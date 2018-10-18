---
<<<<<<< 标头标题： NativeError 属性 (ADO) TOCTitle: NativeError 属性 (ADO) === 标题： NativeError 属性 (ADO) TOCTitle: NativeError 属性 (ADO)
>>>>>>> 母版页 ms:assetid: 9f4d4064-5ee7-20f8-fd54-2cb2eae64d7b ms:mtpsurl: https://msdn.microsoft.com/library/JJ249731(v=office.15) ms:contentKeyID: 48546685 ms.date: 09/18/2015 mtps_version: office.15.aspx
---

<<<<<<< 标头
# <a name="nativeerror-property-ado"></a>NativeError 属性 (ADO)
=======
# <a name="nativeerror-property-ado"></a>NativeError 属性 (ADO)
>>>>>>> master


**适用于**： Access 2013 |Office 2013

指示给定 [Error](error-object-ado.md) 对象特定于提供程序的错误代码。

<<<<<<< 标头
## <a name="return-value"></a>返回值
=======
## <a name="return-value"></a>返回值
>>>>>>> master

返回一个 **Long** 值，指示错误代码。

## <a name="remarks"></a>备注

使用 **NativeError** 属性可为特定的 **Error** 对象检索特定于数据库的错误信息。例如，将 Microsoft ODBC Provider for OLE DB 和 Microsoft SQL Server 数据库一起使用时，从 SQL Server 生成的本机错误代码将通过 ODBC 和 ODBC Provider 传递到 ADO **NativeError** 属性。

