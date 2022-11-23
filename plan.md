
# 枚举类型

```python
from enum import Enum

class State(Enum):
	INACTIVE = 0
	ACTIVE = 1
```
- 使用 `print(State.ACTIVE)` 将返回 `State.ACTIVE` 而不是 `1`
- 枚举中分配的数字可以达到相同的效果： `print(State(1))` 将打印 `State.ACTIVE` 
- 使用方括号符号 `State['ACTIVE']` 也是如此

- 可以使用 `State.ACTIVE.value` 获取具体值
- 枚举类型可以被当作**常量**使用


python 随机布尔值
```python
bool(random.getrandbits(1))
```

- 写一个Fedora37的安装和卸载软件的脚本
