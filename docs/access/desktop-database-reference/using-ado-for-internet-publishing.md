---
title: 使用 ADO for Internet Publishing
TOCTitle: Using ADO for Internet Publishing
ms:assetid: 1e829783-fc12-e303-6f12-2df1ca96cb0f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248975(v=office.15)
ms:contentKeyID: 48543622
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e63e765461eec1c89f3e3dc04d35f1bf88a3c578
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25997621"
---
# <a name="using-ado-for-internet-publishing"></a>使用 ADO for Internet publishing


**适用于**： Access 2013、 Office 2013



[OLE DB Provider for Internet Publishing](the-ole-db-provider-for-internet-publishing.md) 中显示了一个用 ADO 访问异类数据的具体示例。 本节中的示例将特定于使用 Internet Publishing Provider 时, 异构数据，如电子邮件存储提供程序对其他提供程序中使用 ADO 时应类似所述的原则。

## <a name="urls"></a>URL

统一资源定位器 (URL) 可作为连接字符串和命令文本的替代，用于指定数据源和文件与目录位置。您可以将 URL 用于现有的 [Connection](connection-object-ado.md) 和 **Recordset** 对象以及 **Record** 和 **Stream** 对象。

有关使用 URL 的详细信息，请参阅[绝对 URL 和相对 URL](absolute-and-relative-urls.md)。

## <a name="record-fields"></a>记录字段

异类数据与同类数据之间的差别在于，前者的每个数据行或 **记录** 都有不同的列集或 **字段** 。而后者的每个数据行具有相同的列集。有关特定于 Internet Publishing Provider 的字段的详细信息，请参阅 [记录和提供程序提供的字段](records-and-provider-supplied-fields.md)。

## <a name="appending-new-fields"></a>追加新字段

以下是几个新增的 ADO 对象，可以与 **Record** 和 **Stream** 对象一起使用。

  - [Fields](fields-collection-ado.md) 集合的 [Append](append-method-ado.md) 方法，用于在集合中创建和添加 [Field](field-object-ado.md) 对象，还可用于指定 **Field** 的值。

  - [Update](update-method-ado.md) 方法，用于完成集合中字段的添加和删除。

  - 您可以通过简单地为未定义字段或以前删除的字段赋值来创建字段，以作为 **Append** 方法的快捷方式和替代方式。

## <a name="see-also"></a>另请参阅

- [Internet Publishing 方案主题](internet-publishing-scenario.md)