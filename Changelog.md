### v1.8.5 (09-Jun-2018)

- Fixed exception messages not appearing in Visual Studio's exception popup.

### v1.8.4 (09-Mar-2018)

- `StandardErrorException` now shows the value of `StandardError` in `Message`.

### v1.8.3 (03-Mar-2018)

- Added `ICli` to aid in testing.

### v1.8.2 (02-Feb-2018)

- Made input model classes more accessible by removing immutability.
- `Cli` now throws exception if used after getting disposed.

### v1.8.1 (25-Jan-2018)

- Fixed another process leak when canceling synchronous `Execute`.

### v1.8 (25-Jan-2018)

- Refactored additional `Cli` constructor parameters into a separate class called `CliSettings`. This is breaking if you used to supply more than 1 parameter to the constructor.
- `Execute` and `ExecuteAsync` no longer depend on process getting successfully killed. An attempt to kill it is made but if it's not successful, no exception is thrown.
- All `CancellationToken` callbacks are now exception-safe.
- Fixed an issue where `CancellationToken` would throw an out of scope exception when the process could not be killed.
- Fixed a race condition when an execution task is completed and canceled at the same time.

### v1.7.5 (21-Jan-2018)

- Added `EncodingSettings` to customize stream encoding.
- Added some ReSharper annotations to improve warnings and suggestions.

### v1.7.4 (10-Jan-2018)

- Execution start and exit times are now calculated separately, without accessing `Process` instance.
- Execution start and exit times are now `DateTimeOffset` instead of `DateTime`.
- Fixed an issue that prevented CliWrap from properly working on Linux.