---
<<<<<<< 标头标题： 类型属性 (ADO) TOCTitle： 类型属性 (ADO) === 标题： Type 属性 (ADO) TOCTitle: Type 属性 (ADO)
>>>>>>> 母版页 ms:assetid: 14d99172-2145-05ae-620b-459ba097f05c ms:mtpsurl: https://msdn.microsoft.com/library/JJ248914(v=office.15) ms:contentKeyID: 48543397 ms.date: 09/18/2015 mtps_version: office.15.aspx
---

<<<<<<< 标头
# <a name="type-property-ado"></a>Type 属性 (ADO)
=======
# <a name="type-property-ado"></a>Type 属性 (ADO)
>>>>>>> master


**适用于**： Access 2013 |Office 2013

指示 [Parameter](parameter-object-ado.md)、[Field](field-object-ado.md) 或 [Property](property-object-ado.md) 对象的操作类型或数据类型。

<<<<<<< 标头
## <a name="settings-and-return-values"></a>设置和返回值
=======
## <a name="settings-and-return-values"></a>设置和返回值
>>>>>>> master

设置或返回一个 [DataTypeEnum](datatypeenum.md) 值。

## <a name="remarks"></a>备注

对于 **Parameter** 对象， **Type** 属性为可读/写属性。对于已追加到 **Record** 的 [Fields](fields-collection-ado.md) 集合中的新 [Field](record-object-ado.md) 对象，仅在指定了 **Field** 的 [Value](value-property-ado.md) 属性并且数据提供程序通过调用 **Fields** 集合的 **Update** 方法成功添加了新的 [Field](update-method-ado.md) 后， **Type** 才为可读/写。

对于所有其他对象， **Type** 属性为只读属性。

