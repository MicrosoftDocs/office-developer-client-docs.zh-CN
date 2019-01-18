---
title: ParentURL 属性 (ADO)
TOCTitle: ParentURL property (ADO)
ms:assetid: ec7ec476-6f9e-8486-fe02-74995975df5c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250200(v=office.15)
ms:contentKeyID: 48548517
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8e3735147f813d904c206910ff319913f056946e
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28707813"
---
# <a name="parenturl-property-ado"></a>ParentURL 属性 (ADO)

**适用于**： Access 2013、 Office 2013

指示指向当前 [Record](record-object-ado.md) 对象的父 **Record** 的绝对 URL 字符串。

## <a name="return-value"></a>返回值

返回一个 **String** 值，指示父 **Record** 的 URL。

## <a name="remarks"></a>备注

**ParentURL** 属性由用于打开 **Record** 对象的源决定。例如，可以通过包含 **ActiveConnection** 属性引用的目录的相对路径名称的源打开 [Record](activeconnection-property-ado.md) 。

假定"second"是"first"下包含的文件夹。通过以下代码打开 **Record** 对象：

```vb
    record.ActiveConnection = "https://first"
    record.Open "second"
```

现在， **ParentURL**属性的值是**ParentURL**属性"https://first"， **activeconnection 的值**相同。

源也可能是绝对 URL，例如，"https://first/second"。 **ParentURL**属性值为"https://first"，上面的级别。 **ParentURL**属性值为"https://first"，"第二个"上方的级别。

以下情况下，此属性为空值：

- 当前对象没有父对象，例如，如果 **Record** 对象表示根目录。

- **Record** 对象表示无法通过 URL 指定的实体。

此属性为只读。


> [!NOTE]
> - [!注释] 此属性仅受文档源提供程序支持，如 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。有关详细信息，请参阅[记录和提供程序提供的字段](records-and-provider-supplied-fields.md)。
> - [!注释] 使用 HTTP 架构的 URL 将自动调用 Microsoft OLE DB Provider for Internet Publishing。 有关详细信息，请参阅[绝对 URL 和相对 URL](absolute-and-relative-urls.md)。 
> - [!注释] 如果当前记录包含来自 ADO **Recordset** 的数据记录，则访问 **ParentURL** 属性将导致运行时错误，指示没有可能的 URL。


