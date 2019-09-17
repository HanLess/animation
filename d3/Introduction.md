* https://d3js.org/#introduction

#### 插入数据

```
d3.selectAll("p")
  .data([4, 8, 15, 16, 23, 42])
    .style("font-size", function(d) { return d + "px"; });
```

#### 根据数据增加、减少节点（ enter | exit ）

绑定数据：

```
var p = d3.select("body")
  .selectAll("p")
  .data([4, 8, 15, 16, 23, 42])
  .text(function(d) { return d; });
```

#### enter

如果此时 p 节点的数量少于 6 个

```
p.enter().append("p")
    .text(function(d) { return d; });
```

这时会自动补齐，补齐后 p 节点的数量等于 6

#### exit

```
p.exit().remove();
```

如果此时 p 节点的数量大于 6，调用 exit().remove() 后，数量减少至 6

#### enter 方法是重点，根据数据动态生成节点





