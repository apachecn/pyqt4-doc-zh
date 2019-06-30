# QAudio Class Reference

## [[QtMultimedia](index.htm) module]

该QAudio命名空间包含用于音频类的枚举。[More...](#details)

### Types

*   `enum Error { NoError, OpenError, IOError, UnderrunError, FatalError }`
*   `enum Mode { AudioInput, AudioOutput }`
*   `enum State { ActiveState, SuspendedState, StoppedState, IdleState }`

* * *

## Detailed Description

该QAudio命名空间包含用于音频类的枚举。

* * *

## Type Documentation

```
QAudio.Error
```

| Constant | Value | Description |
| --- | --- | --- |
| `QAudio.NoError` | `0` | 没有错误发生 |
| `QAudio.OpenError` | `1` | 打开音频设备的错误 |
| `QAudio.IOError` | `2` | 在音频设备的读/写时发生错误 |
| `QAudio.UnderrunError` | `3` | 音频数据不被馈送到音频设备以足够快的速率 |
| `QAudio.FatalError` | `4` | 发生不可恢复的错误，音频设备不可用在这个时候。 |

```
QAudio.Mode
```

| Constant | Value | Description |
| --- | --- | --- |
| `QAudio.AudioOutput` | `1` | 音频输出装置 |
| `QAudio.AudioInput` | `0` | 音频输入设备 |

```
QAudio.State
```

| Constant | Value | Description |
| --- | --- | --- |
| `QAudio.ActiveState` | `0` | 音频数据被处理时，该状态被设置在开始后（ ）被调用时，虽然音频数据是可用以进行处理。 |
| `QAudio.SuspendedState` | `1` | 音频设备处于暂停状态，这种状态才会进入暂停后， （ ）被调用。 |
| `QAudio.StoppedState` | `2` | 音频设备是封闭的，不处理任何音频数据 |
| `QAudio.IdleState` | `3` | 该[QIODevice](qiodevice.html)在没有任何数据和音频系统的缓冲区是空的通过，这种状态开始后设置（ ）被调用，而没有音频数据可被处理。 |