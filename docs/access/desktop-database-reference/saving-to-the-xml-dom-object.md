---
title: 保存到 XML DOM 对象
TOCTitle: Saving to the XML DOM object
ms:assetid: 3c61fc30-9862-347b-c215-08597eccfead
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249160(v=office.15)
ms:contentKeyID: 48544318
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 95026d878270757c983e42164c92923570c898c6
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28699910"
---
# <a name="saving-to-the-xml-dom-object"></a><span data-ttu-id="90aa6-102">保存到 XML DOM 对象</span><span class="sxs-lookup"><span data-stu-id="90aa6-102">Saving to the XML DOM object</span></span>

<span data-ttu-id="90aa6-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="90aa6-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="saving-to-the-xml-dom-object"></a><span data-ttu-id="90aa6-104">保存到 XML DOM 对象</span><span class="sxs-lookup"><span data-stu-id="90aa6-104">Saving to the XML DOM Object</span></span>

<span data-ttu-id="90aa6-105">可以将 **Recordset** 以 XML 格式保存到 MSXML DOM 对象实例中，如以下 Visual Basic 代码所示：</span><span class="sxs-lookup"><span data-stu-id="90aa6-105">You can save a **Recordset** in XML format to an instance of an MSXML DOM object, as shown in the following Visual Basic code:</span></span>

```vb 
 
Dim xDOM As New MSXML.DOMDocument 
Dim rsXML As New ADODB.Recordset 
Dim sSQL As String, sConn As String 
     
sSQL = "SELECT customerid, companyname, contactname FROM customers" 
sConn="Provider=Microsoft.Jet.OLEDB.4.0;Data Source=D:\Program Files" & _ 
        "\Common Files\System\msadc\samples\NWind.mdb" 
rsXML.Open sSQL, sConn 
rsXML.Save xDOM, adPersistADO   'Save Recordset directly into a DOM tree. 
... 
```

