---
title: XSLT 转换
TOCTitle: XSLT Transformations
ms:assetid: 6a19310d-027f-e8d6-9859-0b545ae7e2f1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249418(v=office.15)
ms:contentKeyID: 48545425
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7120ec08a6a222293fc53c5a98f62c50fd5b3621
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28722597"
---
# <a name="xslt-transformations"></a>XSLT 转换


**适用于**： Access 2013、 Office 2013

## <a name="xslt-transformations"></a>XSLT 转换

可以将 XSLT 应用于所生成的 XML，以便将 XML 转换为其他格式。了解 ADO 中的 XML 格式有助于开发 XSLT 模板，该模板将 XML 转换为对用户更友好的形式。

例如，您知道， **Recordset** 的每一行都可以另存为 rs:data 元素内部的 rs:data 元素。同样， **Recordset** 中的每个字段都可以另存为此元素的属性-值对。

可以将下面的 XSLT 脚本应用于前面部分显示的 XML，以便将 XML 转换为要显示在浏览器中的 HTML 表：

```xml 
 
<?xml version="1.0" encoding="ISO-8859-1"?> 
<html xmlns:xsl="https://www.w3.org/TR/WD-xsl"> 
<body STYLE="font-family:Arial, helvetica, sans-serif; font-size:12pt; background-color:white"> 
<table border="1" style="table-layout:fixed" width="600"> 
  <col width="200"></col> 
  <tr bgcolor="teal"> 
    <th><font color="white">CustomerId</font></th> 
    <th><font color="white">CompanyName</font></th> 
    <th><font color="white">ContactName</font></th> 
  </tr> 
<xsl:for-each select="xml/rs:data/z:row"> 
  <tr bgcolor="navy"> 
    <td><font color="white"><xsl:value-of select="@CustomerID"/></font></td> 
    <td><font color="white"><xsl:value-of select="@CompanyName"/></font></td> 
    <td><font color="white"><xsl:value-of select="@ContactName"/></font></td>  
  </tr> 
</xsl:for-each> 
</table> 

</body> 
</html> 
```

XSLT 将 ADO **Save** 方法生成的 XML 流转换为一个 HTML 表，该表显示 **Recordset** 的每个字段以及表标题。可以为表标题和行指定不同的字体和颜色。

