## [ torch 参数更多 ] torch.Tensor.divide_

### [torch.Tensor.divide_](https://pytorch.org/docs/stable/generated/torch.Tensor.divide_.html)

```python
torch.Tensor.divide_(other, *, rounding_mode=None)
```

### [paddle.Tensor.divide_]()

```python
paddle.Tensor.divide_(y)
```

Pytorch 相比 Paddle 支持更多其他参数，具体如下：

### 参数映射

| PyTorch       | PaddlePaddle | 备注                                                                                |
| ------------- | ------------ | ----------------------------------------------------------------------------------- |
| other         | y            | 表示输入的 Tensor ，仅参数名不一致。                                                   |
| rounding_mode | -            | 用于指定在执行截断除法时的舍入模式。可选值为 'floor'(向下取整) 或 'trunc'(向零取整)。 Paddle 无此参数，需要转写。Paddle 可通过组合 paddle.trunc 或 paddle.floor 实现。 |

### 转写示例

```python
# torch 写法
x = torch.tensor([4, 8, 12], dtype=torch.float32)
y = torch.tensor([3, 4, 5], dtype=torch.float32)
z1 = x.divide_(y, rounding_mode='floor') # 向下取整
z2 = x.divide_(y, rounding_mode='trunc') # 向零取整

# paddle 写法
x = paddle.to_tensor([4, 8, 12], dtype='float32')
y = paddle.to_tensor([3, 4, 5], dtype='float32')
z1 = x.divide_(y).floor_()  # 向下取整
z2 = x.divide_(y).trunc_()  # 向零取整
```
