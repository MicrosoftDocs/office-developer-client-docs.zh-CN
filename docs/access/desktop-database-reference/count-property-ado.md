---
<<<<<<< 标头标题： Count 属性 (ADO) TOCTitle: Count 属性 (ADO) === 标题： Count 属性 (ADO) TOCTitle: Count 属性 (ADO)
>>>>>>> 母版页 ms:assetid: b59f9581-ffd1-471d-44fa-3c1bb812e140 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249871(v=office.15) ms:contentKeyID: 48547253 ms.date: 09/18/2015 mtps_version: office.15.aspx
---

<<<<<<< 标头
# <a name="count-property-ado"></a>Count 属性 (ADO)
=======
# <a name="count-property-ado"></a>Count 属性 (ADO)
>>>>>>> master


**适用于**： Access 2013 |Office 2013

指示集合中的对象数。

<<<<<<< 标头
## <a name="return-value"></a>返回值
=======
## <a name="return-value"></a>返回值
>>>>>>> master

返回 **Long** 值。

## <a name="remarks"></a>备注

使用 **Count** 属性可确定在给定集合中有多少个对象。

由于集合中的成员是从零开始进行编号的，因此应始终将循环编写为从第零个成员开始，而在 **Count** 属性的值减 1 处终止。如果在使用 Microsoft Visual Basic，而希望在不检查 **Count** 属性的情况下遍历集合的成员，则请使用 **For** **Each...Next** 命令。

如果 **Count** 属性为零，则表明集合中没有对象。

