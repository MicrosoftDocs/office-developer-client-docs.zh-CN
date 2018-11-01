---
title: FieldEnum （访问桌面数据库参考 （英文）
TOCTitle: FieldEnum
ms:assetid: fbd415c0-d6b4-278f-318b-98432c013634
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250289(v=office.15)
ms:contentKeyID: 48548876
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 6975017ed8867d794dce189de74f617636b9f223
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25886659"
---
# <a name="fieldenum"></a><span data-ttu-id="c5e66-102">FieldEnum</span><span class="sxs-lookup"><span data-stu-id="c5e66-102">FieldEnum</span></span>

<span data-ttu-id="c5e66-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c5e66-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c5e66-104">指定在 [Record](record-object-ado.md) 对象的 [Fields](fields-collection-ado.md) 集合中引用的特殊字段。</span><span class="sxs-lookup"><span data-stu-id="c5e66-104">Specifies the special fields referenced in a [Record](record-object-ado.md) object's [Fields](fields-collection-ado.md) collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5e66-105">说明</span><span class="sxs-lookup"><span data-stu-id="c5e66-105">Remarks</span></span>

<span data-ttu-id="c5e66-p101">这些常量提供指向访问与 **Record** 关联的特殊字段的"快捷方式"。从 [Fields](field-object-ado.md) 集合中检索 **Field** 对象，然后使用 **Field** 对象的 [Value](value-property-ado.md) 属性获取其内容。</span><span class="sxs-lookup"><span data-stu-id="c5e66-p101">These constants provide a "shortcut" to accessing special fields associated with a **Record**. Retrieve the [Field](field-object-ado.md) object from the **Fields** collection, and then obtain its contents with the **Field** object's [Value](value-property-ado.md) property.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c5e66-108">常量</span><span class="sxs-lookup"><span data-stu-id="c5e66-108">Constant</span></span></p></th>
<th><p><span data-ttu-id="c5e66-109">值</span><span class="sxs-lookup"><span data-stu-id="c5e66-109">Value</span></span></p></th>
<th><p><span data-ttu-id="c5e66-110">说明</span><span class="sxs-lookup"><span data-stu-id="c5e66-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5e66-111"><strong>adDefaultStream</strong></span><span class="sxs-lookup"><span data-stu-id="c5e66-111"><strong>adDefaultStream</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e66-112">-1</span><span class="sxs-lookup"><span data-stu-id="c5e66-112">-1</span></span></p></td>
<td><p><span data-ttu-id="c5e66-113">引用包含与 <strong>Record</strong> 关联的默认 <a href="stream-object-ado.md">Stream</a> 对象的字段。</span><span class="sxs-lookup"><span data-stu-id="c5e66-113">References the field containing the default <a href="stream-object-ado.md">Stream</a> object associated with a <strong>Record</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e66-114"><strong>adRecordURL</strong></span><span class="sxs-lookup"><span data-stu-id="c5e66-114"><strong>adRecordURL</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e66-115">-2</span><span class="sxs-lookup"><span data-stu-id="c5e66-115">-2</span></span></p></td>
<td><p><span data-ttu-id="c5e66-116">引用包含当前 <strong>Record</strong> 的绝对 URL 字符串的字段。</span><span class="sxs-lookup"><span data-stu-id="c5e66-116">References the field containing the absolute URL string for the current <strong>Record</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

