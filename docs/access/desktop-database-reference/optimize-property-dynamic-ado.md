---
title: "Optimize 属性 \x97 动态 (ADO)"
TOCTitle: Optimize Property--Dynamic (ADO)
ms:assetid: 2253b052-2d8a-f6f0-f8b8-f56e79d243de
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249001(v=office.15)
ms:contentKeyID: 48543705
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6c31950eda813ee4f3f07145d28a83106cf86b3f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466641"
---
# <a name="optimize-property--dynamic-ado"></a><span data-ttu-id="edc69-102">Optimize 属性  动态 (ADO)</span><span class="sxs-lookup"><span data-stu-id="edc69-102">Optimize Property--Dynamic (ADO)</span></span>


<span data-ttu-id="edc69-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="edc69-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="edc69-104">指定是否应在字段上创建索引。</span><span class="sxs-lookup"><span data-stu-id="edc69-104">Specifies whether an index should be created on a field.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="edc69-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="edc69-105">Settings and Return Values</span></span>

<span data-ttu-id="edc69-106">设置或返回一个 **Boolean** 值，指示是否应创建索引。</span><span class="sxs-lookup"><span data-stu-id="edc69-106">Sets or returns a **Boolean** value that indicates whether an index should be created.</span></span>

## <a name="remarks"></a><span data-ttu-id="edc69-107">备注</span><span class="sxs-lookup"><span data-stu-id="edc69-107">Remarks</span></span>

<span data-ttu-id="edc69-p101">索引可提高在 [Recordset](recordset-object-ado.md) 中对值进行查找和排序的操作性能。索引由 ADO 内部使用  无法在应用程序中显式访问或使用。</span><span class="sxs-lookup"><span data-stu-id="edc69-p101">An index can improve the performance of operations that find or sort values in a [Recordset](recordset-object-ado.md). The index is internal to ADO — you cannot explicitly access or use it in your application.</span></span>

<span data-ttu-id="edc69-p102">若要在字段上创建索引，请将 **Optimize** 属性设置为 **True** 。若要删除索引，请将此属性设置为 **False** 。</span><span class="sxs-lookup"><span data-stu-id="edc69-p102">To create an index on a field, set the **Optimize** property to **True**. To delete the index, set this property to **False**.</span></span>

<span data-ttu-id="edc69-112">**Optimize** 是一个动态属性，会在 [CursorLocation](field-object-ado.md) 属性设置为 [adUseClient](properties-collection-ado.md) 时追加到 [Field](cursorlocation-property-ado.md) 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="edc69-112">**Optimize** is a dynamic property appended to the [Field](field-object-ado.md) object [Properties](properties-collection-ado.md) collection when the [CursorLocation](cursorlocation-property-ado.md) property is set to **adUseClient**.</span></span>

<span data-ttu-id="edc69-113">**用法**</span><span class="sxs-lookup"><span data-stu-id="edc69-113">**Usage**</span></span>

```vb
    Dim rs As New Recordset
    Dim fld As Field
    rs.CursorLocation = adUseClient      'Enable index creation
    rs.Fields.Append "Field1", adChar, 35, adFldIsNullable
    rs.Open
    Set fld = rs.Fields(0)
    fld.Properties("Optimize") = True    'Create an index
    fld.Properties("Optimize") = False   'Delete an index
```
