---
<<<<<<< 标头标题： 值属性 (ADO) TOCTitle： 值属性 (ADO) === 标题： Value 属性 (ADO) TOCTitle: Value 属性 (ADO)
>>>>>>> 母版页 ms:assetid: ff21d122-98e3-2b48-d92f-e696b8079fc5 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250310(v=office.15) ms:contentKeyID: 48548958 ms.date: 09/18/2015 mtps_version: office.15.aspx
---

<<<<<<< 标头
# <a name="value-property-ado"></a>Value 属性 (ADO)
=======
# <a name="value-property-ado"></a>Value 属性 (ADO)
>>>>>>> master


**适用于**： Access 2013 |Office 2013

指示赋给 [Field](field-object-ado.md)、[Parameter](parameter-object-ado.md) 或 [Property](property-object-ado.md) 对象的值。

<<<<<<< 标头
## <a name="settings-and-return-values"></a>设置和返回值
=======
## <a name="settings-and-return-values"></a>设置和返回值
>>>>>>> master

设置或返回一个指示对象的值的 **Variant** 值。默认值取决于 [Type](type-property-ado.md) 属性。

## <a name="remarks"></a>备注

使用 **Value** 属性可以设置或返回来自 **Field** 对象的数据，设置或返回 **Parameter** 对象的参数值，或者设置或返回 **Property** 对象的属性设置。 **Value** 属性为可读/写还是只读属性取决于许多因素，有关详细信息，请参阅各个对象主题。

ADO 允许设置和返回 **Value** 属性的长二进制数据。


> [!NOTE]
> <P>[!注释] 对于 <STRONG>Parameter</STRONG> 对象，ADO 只从提供程序那里读取一次 <STRONG>Value</STRONG> 属性。如果某命令包含 <STRONG>Value</STRONG> 属性为空的 <STRONG>Parameter</STRONG> 并且将使用该命令来创建 <A href="recordset-object-ado.md">Recordset</A>，则请确保首先关闭 <STRONG>Recordset</STRONG> ，然后再检索 <STRONG>Value</STRONG> 属性。否则，对于某些提供程序， <STRONG>Value</STRONG> 属性可能为空，并且不包含正确的值。</P>



对于已追加到 **Record** 对象的 [Fields](fields-collection-ado.md) 集合中的新 [Field](record-object-ado.md) 对象，必须先设置 **Value** 属性，然后才能指定其他任何 **Field** 属性。首先，必须为 **Value** 属性赋予特定值，并对 [Fields](update-method-ado.md) 集合调用 **Update**。然后，可以访问诸如 [Type](type-property-ado.md) 或 [Attributes](attributes-property-ado.md) 等其他属性。

