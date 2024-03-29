# 언제 0이 될까?
```python
1e-323.__eq__(0)
False
1e-323.__eq__(0.0)
False

1e-324.__eq__(0)
True
1e-324.__eq__(0.0)
True
```
