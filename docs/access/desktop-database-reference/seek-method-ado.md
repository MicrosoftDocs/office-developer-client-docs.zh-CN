---
title: Seek 方法-ActiveX 数据对象 (ADO)
TOCTitle: Seek method (ADO)
ms:assetid: cf0f133b-31f2-a2df-6cf3-1b5fa73b516c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250027(v=office.15)
ms:contentKeyID: 48547802
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 321040a39b02f31f0265df6e91748df13c05032c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28726300"
---
# <a name="seek-method-ado"></a><span data-ttu-id="06e25-102">Seek 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="06e25-102">Seek method (ADO)</span></span>

<span data-ttu-id="06e25-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="06e25-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="06e25-104">可搜索 [Recordset](recordset-object-ado.md) 的索引，以快速找到与指定值匹配的行，并将当前行位置更改为该行。</span><span class="sxs-lookup"><span data-stu-id="06e25-104">Searches the index of a [Recordset](recordset-object-ado.md) to quickly locate the row that matches the specified values, and changes the current row position to that row.</span></span>

## <a name="syntax"></a><span data-ttu-id="06e25-105">语法</span><span class="sxs-lookup"><span data-stu-id="06e25-105">Syntax</span></span>

<span data-ttu-id="06e25-106">*记录集*。Seek*KeyValues*， *SeekOption*</span><span class="sxs-lookup"><span data-stu-id="06e25-106">*recordset*.Seek*KeyValues*, *SeekOption*</span></span>

## <a name="parameters"></a><span data-ttu-id="06e25-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="06e25-107">Parameters</span></span>

|<span data-ttu-id="06e25-108">参数</span><span class="sxs-lookup"><span data-stu-id="06e25-108">Parameter</span></span>|<span data-ttu-id="06e25-109">说明</span><span class="sxs-lookup"><span data-stu-id="06e25-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="06e25-110">*KeyValues*</span><span class="sxs-lookup"><span data-stu-id="06e25-110">*KeyValues*</span></span> |<span data-ttu-id="06e25-p101">**变量型** 值的数组。索引由一列或多列组成，而数组包含一个用于与每个相应列进行比较的值。</span><span class="sxs-lookup"><span data-stu-id="06e25-p101">An array of **Variant** values. An index consists of one or more columns and the array contains a value to compare against each corresponding column.</span></span>|
|<span data-ttu-id="06e25-113">*SeekOption*</span><span class="sxs-lookup"><span data-stu-id="06e25-113">*SeekOption*</span></span> |<span data-ttu-id="06e25-114">[SeekEnum](seekenum.md) 值，用于指定在索引列与相应 *KeyValues* 之间进行比较的类型。</span><span class="sxs-lookup"><span data-stu-id="06e25-114">A [SeekEnum](seekenum.md) value that specifies the type of comparison to be made between the columns of the index and the corresponding *KeyValues*.</span></span>|

## <a name="remarks"></a><span data-ttu-id="06e25-115">备注</span><span class="sxs-lookup"><span data-stu-id="06e25-115">Remarks</span></span>

<span data-ttu-id="06e25-116">**Seek**方法结合使用的[索引](index-property-ado.md)属性，如果基础提供程序支持对**Recordset**对象的索引。</span><span class="sxs-lookup"><span data-stu-id="06e25-116">Use the **Seek** method in conjunction with the [Index](index-property-ado.md) property if the underlying provider supports indexes on the **Recordset** object.</span></span> <span data-ttu-id="06e25-117">使用[支持](supports-method-ado.md)**(adSeek)** 方法以确定基础提供程序是否支持**Seek**和**Supports(adIndex)** 方法以确定提供程序是否支持索引。</span><span class="sxs-lookup"><span data-stu-id="06e25-117">Use the [Supports](supports-method-ado.md)**(adSeek)** method to determine whether the underlying provider supports **Seek**, and the **Supports(adIndex)** method to determine whether the provider supports indexes.</span></span> <span data-ttu-id="06e25-118">（例如， [OLE DB Provider for Microsoft Jet](microsoft-ole-db-provider-for-microsoft-jet.md)支持**Seek**和**Index**。）</span><span class="sxs-lookup"><span data-stu-id="06e25-118">(For example, the [OLE DB Provider for Microsoft Jet](microsoft-ole-db-provider-for-microsoft-jet.md) supports **Seek** and **Index**.)</span></span>

<span data-ttu-id="06e25-p103">如果 **Seek** 找不到所需的行，不会发生错误，只是将该行置于 **Recordset** 的末尾。将 **Index** 属性设置为所需索引，然后执行此方法。</span><span class="sxs-lookup"><span data-stu-id="06e25-p103">If **Seek** does not find the desired row, no error occurs, and the row is positioned at the end of the **Recordset**. Set the **Index** property to the desired index before executing this method.</span></span>

<span data-ttu-id="06e25-p104">只有服务器端游标才支持此方法。当 **Recordset** 对象的 [CursorLocation](cursorlocation-property-ado.md) 属性值为 **adUseClient** 时，不支持 Seek。</span><span class="sxs-lookup"><span data-stu-id="06e25-p104">This method is supported only with server-side cursors. Seek is not supported when the **Recordset** object's [CursorLocation](cursorlocation-property-ado.md) property value is **adUseClient**.</span></span>

<span data-ttu-id="06e25-123">仅当事先使用 **adCmdTableDirect** 的 [CommandTypeEnum](commandtypeenum.md) 值打开 **Recordset** 对象时，才能使用此方法。</span><span class="sxs-lookup"><span data-stu-id="06e25-123">This method can only be used when the **Recordset** object has been opened with a [CommandTypeEnum](commandtypeenum.md) value of **adCmdTableDirect**.</span></span>

