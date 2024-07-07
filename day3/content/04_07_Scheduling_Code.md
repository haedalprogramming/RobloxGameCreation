# Scheduling Code

## 목차
- [Scheduling Code](#scheduling-code)
  - [목차](#목차)
    - [일반적인 메서드](#일반적인-메서드)
      - [task.spawn](#taskspawn)
      - [task.defer](#taskdefer)
      - [task.delay](#taskdelay)
      - [task.wait](#taskwait)
  - [출처](#출처)
  - [다음](#다음)

---

코드 스케줄링은 특정 작업이나 사이클이 완료된 후 코드를 실행하거나 특정 기간 동안 코드를 지연시키는 등 여러 상황에서 유용합니다. `task` 라이브러리를 사용하여 Roblox의 Task Scheduler를 최적화하여 코드를 관리하고 스케줄링할 수 있습니다. 추가 기능이 있는 `coroutine`이라는 유사한 라이브러리도 사용할 수 있습니다.

### 일반적인 메서드

다음은 코드를 스케줄링하는 데 사용되는 일반적인 `task` 메서드입니다. 코드가 최적의 성능으로 실행되도록 하려면 이전 스케줄링 메서드인 `Global.RobloxGlobals.wait()` 대신 이 메서드를 사용해야 합니다.

<Alert severity="warning">
`Global.RobloxGlobals.spawn()`, `Global.RobloxGlobals.delay()`, `Global.RobloxGlobals.wait()`와 같은 이전의 전역 메서드는 유사한 코드 스케줄링 결과를 제공할 수 있지만, `task` 대안보다 최적화되지 않고 구성할 수 있는 옵션이 적습니다. 경험이 이러한 이전 메서드를 사용하는 경우, `task`를 사용하여 경험의 코드가 효율적이고 최신 상태를 유지하도록 해야 합니다.
</Alert>

다음 표는 관련된 이전 전역 메서드와 더 최적화된 선호되는 대안을 나열한 것입니다:

| 이전 전역 메서드                        | Task 메서드                                      | 추가 대안                                         |
| :-------------------------------------- | :----------------------------------------------- | :------------------------------------------------ |
| `wait()`                                | `task.wait()`                            | `RunService.Heartbeat`                       |
| `wait(n)`                               | `task.wait(n)`              |                                                    |
| `spawn(f)`                              | `task.defer(f)`            | `task.delay(0, f)`           |
| `delay(n, f)`                           | `task.delay(n, f)`         |                                                    |
| `spawn(function() f(uv1, ...) end)`    | `task.defer(f, uv1, ...)`  | `task.delay(0, f, uv1, ...)` |
| `delay(n, function() f(uv1, ...) end)` | `task.delay(n, f, uv1, ...)` |                                                    |

#### task.spawn

`task.spawn()`은 스레드나 함수를 가져와 엔진의 스케줄러를 통해 **즉시** 재개합니다. 추가 인수는 재개되는 스레드나 함수로 전달됩니다.

다음 코드 샘플은 객체 집합을 반복하는 동안 yield할 수 있는 함수를 호출할 때 `task.spawn()`을 사용하는 방법의 예입니다:

```lua
local function playerAdded(player)
    ...
    (yield)
end

for _, player in Players:GetPlayers() do
    task.spawn(playerAdded, player)
end
```

#### task.defer

`task.defer()`는 스레드나 함수를 가져와 다음 [재개 사이클](https://devforum.roblox.com/t/beta-deferred-lua-event-handling)까지 지연한 후 엔진의 스케줄러와 함께 재개합니다. 추가 인수는 재개되는 스레드나 함수로 전달됩니다.

일반적으로 스레드가 즉시 실행되지 않아도 될 때 `task.spawn()`과 유사한 동작을 원할 때 사용해야 합니다. 다음 코드 샘플은 `"A"`에 대한 `print()` 문이 `"B"`의 `print()` 문이 실행된 후 지연되는 방법을 보여줍니다:

```lua
task.defer(print, "A")
print("B")
--> B
--> A
```

<Alert severity="info">
`task.defer()`는 스레드가 가능한 빨리(즉시가 아닌) 재개되도록 스케줄링하는 최적화된 `spawn()` 버전입니다.
</Alert>

#### task.delay

`task.delay()`는 스레드나 함수를 가져와 지정된 시간이 경과한 후 다음 `Heartbeat` 단계에서 재개하도록 스케줄링합니다. 스레드는 내장된 오류 처리 및 기타 엔진 기능을 지원하며 재개됩니다. 추가 인수는 재개되는 스레드나 함수로 전달됩니다.

실제 지연 시간이 다를 수 있기 때문에, 다음 코드 샘플은 현재 시간을 인수로 전달하여 지연 시간을 계산하는 방법을 보여줍니다:

```lua
task.delay(2, function(scheduledTime)
    print(os.clock() - scheduledTime) --> 2.038702
end, os.clock())
```

지연 시간이 0이면 스레드나 함수는 다음 단계에서 재개됩니다.

<Alert severity="info">
`task.delay()`는 스레드가 일정 시간이 경과한 후 재개되도록 스케줄링하는 최적화된 `delay()` 버전입니다.
</Alert>

#### task.wait

`task.wait()`는 주어진 기간(초) 동안 현재 스레드를 대기시킨 다음, 다음 `Heartbeat` 단계에서 스레드를 재개합니다.

실제 대기 시간은 다를 수 있습니다. 다음 코드 샘플은 이 메서드가 편의를 위해 실제 대기 시간을 반환하는 방법을 보여줍니다:

```lua
local elapsedTime = task.wait(2) -- 2초 대기
print(elapsedTime) --> 2.0792941
```

기간이 지정되지 않은 경우 기본값은 0이며, 이는 스레드가 자동으로 다음 단계에서 재개됨을 의미합니다. 따라서 `task.wait()`는 `RunService.Heartbeat`와 동등한 동작을 합니다.

<Alert severity="info">
`task.wait()`는 일정 시간이 경과한 후 현재 스레드가 재개되도록 스케줄링하는 최적화된 `wait()` 버전입니다.
</Alert>

---
## 출처
 - [Scheduling Code](https://create.roblox.com/docs/scripting/scheduler)

---
## [다음](./04_08_Parallel_Luau.md)