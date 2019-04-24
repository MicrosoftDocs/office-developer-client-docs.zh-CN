---
title: Save 方法-ActiveX 数据对象 (ADO)
TOCTitle: Save method (ADO)
ms:assetid: 02dab13b-f947-b96d-46ea-0def3ed8f28f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248793(v=office.15)
ms:contentKeyID: 48542968
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0a3762c3d4fdb8cc833259b0435b225690d677ce
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308916"
---
# <a name="save-method-ado"></a>Save 方法 (ADO)

**适用于**：Access 2013、Office 2013

可将 [Recordset](recordset-object-ado.md) 保存到文件或 [Stream](stream-object-ado.md) 对象。

## <a name="syntax"></a>语法

*recordset*。保存*目标*, *PersistFormat*

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*Destination* |可选。一个 **变量型** ，表示要保存 **Recordset** 的文件的完整路径名；或 **Stream** 对象的引用。|
|*PersistFormat* |可选。[PersistFormatEnum](persistformatenum.md) 值，用于指定 **Recordset** 的保存格式（XML 或 ADTG）。默认值为 **adPersistADTG** 。|

## <a name="remarks"></a>注解

只能对打开的 **Recordset** 调用 **Save** 方法。使用 [Open](open-method-ado-recordset.md) 方法以便以后从 *Destination* 中还原 **Recordset**。

如果 [Filter](filter-property-ado.md) 属性对于 **Recordset** 有效，则只保存可通过筛选访问的行。如果 **Recordset** 是分层结构，则保存当前子 **Recordset** 及其子级，包括父 **Recordset** 。如果调用子 **Recordset** 的 **Save** 方法，则保存该子记录集及其所有子记录集，但不保存父记录集。

第一次保存 **Recordset** 时，可以选择指定 *Destination*。如果省略 *Destination*，系统将创建新文件，文件名为 **Recordset** 的 [Source](source-property-ado-recordset.md) 属性的值。

在首次保存后调用 **Save** 时，应省略 *Destination*，否则将发生运行时错误。如果随后使用新的 *Destination* 调用 **Save**，则 **Recordset** 会保存到新的目标中。但是，新目标和原来的目标都将打开。

**Save** 不会关闭 **Recordset** 或 *Destination*，因此可以继续使用 **Recordset** 并保存最新的更改。在关闭 **Recordset** 之前，*Destination* 一直是打开的。

由于安全原因， **Save** 方法只允许在 Microsoft Internet Explorer 执行的脚本中使用低安全设置和自定义安全设置。有关安全问题的详细说明，请参阅 Microsoft 数据访问技术文章中 ActiveX 数据对象 (ADO) 技术文章下的"ADO and RDS Security Issues in Microsoft Internet Explorer"（Microsoft Internet Explorer 中的 ADO 和 RDS 安全问题）。

如果在执行异步 **Recordset** 提取、执行或更新操作时调用 **Save** 方法，则将等到异步操作完成后，才执行 **Save** 。

记录的保存是从 **Recordset** 的第一行开始的。 **Save** 方法完成之后，当前行位置被移到 **Recordset** 的第一行。

为获得最佳结果，请用 [Save](cursorlocation-property-ado.md) 方法将 **CursorLocation** 属性设置为 **adUseClient** 。如果提供程序不支持保存 **Recordset** 对象所需的所有功能，则游标服务将提供该功能。

如果在持久化 **Recordset** 时将 **CursorLocation** 属性设置为 **adUseServer** ，则 **Recordset** 的更新功能会受到限制。通常，只允许对单个表进行更新、插入和删除操作（具体取决于提供程序功能）。在此配置中， [Resync](resync-method-ado.md) 方法也不可用。

> [!NOTE]
> [!注释] ADO 不支持保存含有 **adVariant** 、 **adIDispatch** 或 **adIUnknown** 类型 **Fields** 的 **Recordset** ，这样做可能会导致无法预料的结果。

只有条件字符串形式的**筛选器**(例如, "日期\> 12/31/1999") 会影响持久化**Recordset**的内容。 通过 **Bookmark** 数组或使用 **FilterGroupEnum** 中的值创建的 **Filter** 不会影响持久 Recordset 的内容。 这些规则适用于通过客户端或服务器端游标创建的 **Recordset**。

由于 *Destination* 参数可以接受支持 OLE DB IStream 接口的任意对象，因此可以将 **Recordset** 直接保存到 ASP Response 对象。有关详细信息，请参阅 [XML Recordset 持久化方案](xml-recordset-persistence-scenario.md)。

此外，还可以将 **Recordset** 以 XML 格式保存到 MSXML DOM 对象的实例，如以下 Visual Basic 代码所示：

> [!NOTE]
> 在以 XML 格式保存分层 **Recordsets**（数据形状）时有两个限制。其一，如果分层 **Recordset** 中包含挂起更新，则不能保存到 XML。其二，不能保存参数化的分层 **Recordset**。

以 XML 格式保存的 Recordset 采用 UTF-8 格式保存。当此类文件加载到 ADO 流时，Stream 对象不会尝试从流打开 Recordset，除非流的 Charset 属性设置为正确的 UTF-8 值。

