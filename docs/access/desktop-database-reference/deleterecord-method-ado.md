---
title: DeleteRecord 方法 (ADO)
TOCTitle: DeleteRecord method (ADO)
ms:assetid: ba71187f-e580-bba8-f41b-bedfa0bc2b04
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249895(v=office.15)
ms:contentKeyID: 48547370
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8d6ecd408bc2141ef9ff4bec8f6469a70e09bbe1
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28704516"
---
# <a name="deleterecord-method-ado"></a>DeleteRecord 方法 (ADO)

**适用于**： Access 2013、 Office 2013

用于删除由 [Record](record-object-ado.md) 表示的实体。

## <a name="syntax"></a>语法

*记录*。 **DeleteRecord *** 源*，*异步*

## <a name="parameters"></a>Parameters

|参数|说明|
|:--------|:----------|
|*Source* |可选。**字符串型**值，包含用于标识要删除的实体（如文件或目录）的 URL。如果忽略 *Source* 或者指定一个空字符串，将删除由当前 [Record](record-object-ado.md) 表示的实体。如果该 Record 是一个集合记录（**adCollectionRecord** 的 [RecordType](recordtype-property-ado.md)，例如目录），还将删除所有子级（如子目录）。|
|*Async* |可选。一个 **Boolean** 值，为 **True** 时，指定删除操作为异步。|

## <a name="remarks"></a>说明

该方法完成之后，由此 **Record** 表示的对象上的操作可能会失败。由于此 **Record** 的行为将取决于提供程序何时用数据源来更新它，因此 **Record** 的行为变得无法预测，调用 **DeleteRecord** 之后，应关闭此 **Record** 。

如果此 **Record** 是从 [Recordset](recordset-object-ado.md) 获取的，则该操作的结果将不会立即反映到 **Recordset** 中。 关闭并重新打开它，或通过执行的**Recordset**的[Requery](requery-method-ado.md)，或[更新](update-method-ado.md)和[Resync](resync-method-ado.md)方法刷新**Recordset** 。

> [!NOTE]
> [!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。 有关详细信息，请参阅[绝对和相对 Url](absolute-and-relative-urls.md)。


