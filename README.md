# 配置文件

## global
- processNumber：进程数量，填写 -1 进程数量为 CPU核心数x4
- delay：每个请求的间隔时间（每个进程独立计算）

## Stream
- url：请求的链接（可以使用随机函数）
- check：填写正则表达式，与body部分匹配，用于检测是否成功
- method：请求方式，填写POST或GET
- referer：对应Header中的referer
- data：POST提交的数据（可以使用随机函数）

## 随机函数
### 格式
- 全部修改为 ${random.xxx()} 
### 可用函数
- random.qq() 随机QQ号
- random.phone() 随机电话号码
- random.number(长度) 随机指定长度的数字
- random.string(长度) 随机指定长度的字符串
- random.custom(自定义字符 , 长度) 从自定义字符中随机指定长度的字符

# 警告
## 进程数
由于node的限制，无法使用多线程，只能使用多进程，所以请不要把进程数量开太大
否则可能会导致以下结果
1. 电脑死机，严重可能会导致硬件损坏
2. 全家一起断网并且你的运营商给你打电话