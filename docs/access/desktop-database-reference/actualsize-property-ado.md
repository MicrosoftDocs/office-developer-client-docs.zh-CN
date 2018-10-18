---
<<<<<<< 标头标题： ActualSize 属性 (ADO) TOCTitle: ActualSize 属性 (ADO) ms:assetid: 020a414d-e6aa-5fb9-9b77-bd9d10124f8a ms:mtpsurl: https://msdn.microsoft.com/library/JJ248787(v=office.15) ms:contentKeyID: 48542949 ms.date: 09/18/2015 mtps_version: v =office.15
---

# <a name="actualsize-property-ado"></a>ActualSize 属性 (ADO)
=== 标题： ActualSize 属性 (ADO) TOCTitle: ActualSize 属性 (ADO) ms:assetid: 020a414d-e6aa-5fb9-9b77-bd9d10124f8a ms:mtpsurl: https://msdn.microsoft.com/library/JJ248787(v=office.15) ms:contentKeyID: 48542949 ms.date: 10/16/2018 mtps_version: office.15.aspx
---

# <a name="actualsize-property-ado"></a>ActualSize 属性 (ADO)
>>>>>>> master

**适用于**： Access 2013 |Office 2013

指示字段值的实际长度。

<<<<<<< 标头
## <a name="settings-and-return-values"></a>设置和返回值
=======
## <a name="settings-and-return-values"></a>设置和返回值
>>>>>>> master

返回 **Long** 值。某些提供程序可能允许设置此属性来为 BLOB 数据保留空间，此时的默认值为 0。

## <a name="remarks"></a>备注

使用 **ActualSize** 属性可以返回 [Field](field-object-ado.md) 对象值的实际长度。对于所有字段， **ActualSize** 属性都是只读的。如果 ADO 无法确定 **Field** 对象值的长度， **ActualSize** 属性将返回 **adUnknown** 。

<<<<<<< 头**ActualSize**和[DefinedSize](definedsize-property-ado.md)属性会有所不同，如下面的示例中所示。 声明的类型为 **adVarChar** 且最大长度为 50 个字符的 **Field** 对象返回的 **DefinedSize** 属性值为 50，但其返回的 **ActualSize** 属性值为存储在当前记录的字段中的数据的长度。 **DefinedSize** 大于 255 个字节的 **Fields** 将作为可变长度列处理。
=== **ActualSize**和[DefinedSize](definedsize-property-ado.md)属性具有不同。 声明的类型为 **adVarChar** 且最大长度为 50 个字符的 **Field** 对象返回的 **DefinedSize** 属性值为 50，但其返回的 **ActualSize** 属性值为存储在当前记录的字段中的数据的长度。 **DefinedSize** 大于 255 个字节的 **Fields** 将作为可变长度列处理。
>>>>>>> master

