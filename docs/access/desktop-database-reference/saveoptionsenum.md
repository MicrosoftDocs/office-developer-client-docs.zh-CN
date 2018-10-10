---
title: SaveOptionsEnum （访问桌面数据库参考 （英文）
TOCTitle: SaveOptionsEnum
ms:assetid: 2a4e4c7a-6331-7270-0514-cc549c721ffd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249053(v=office.15)
ms:contentKeyID: 48543906
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 68526eca205fb41dd2789ec187514d0f9b11e35f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466437"
---
# <a name="saveoptionsenum"></a><span data-ttu-id="f7476-102">SaveOptionsEnum</span><span class="sxs-lookup"><span data-stu-id="f7476-102">SaveOptionsEnum</span></span>


<span data-ttu-id="f7476-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="f7476-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="f7476-p101">指定当从 [Stream](stream-object-ado.md) 对象进行保存时，应创建文件还是覆盖文件。可以使用 AND 运算符来组合使用这些值。</span><span class="sxs-lookup"><span data-stu-id="f7476-p101">Specifies whether a file should be created or overwritten when saving from a [Stream](stream-object-ado.md) object. The values can be combined with an AND operator.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f7476-106">常量</span><span class="sxs-lookup"><span data-stu-id="f7476-106">Constant</span></span></p></th>
<th><p><span data-ttu-id="f7476-107">值</span><span class="sxs-lookup"><span data-stu-id="f7476-107">Value</span></span></p></th>
<th><p><span data-ttu-id="f7476-108">说明</span><span class="sxs-lookup"><span data-stu-id="f7476-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7476-109"><strong>adSaveCreateNotExist</strong></span><span class="sxs-lookup"><span data-stu-id="f7476-109"><strong>adSaveCreateNotExist</strong></span></span></p></td>
<td><p><span data-ttu-id="f7476-110">1</span><span class="sxs-lookup"><span data-stu-id="f7476-110">1</span></span></p></td>
<td><p><span data-ttu-id="f7476-p102">默认值。指示如果 <em>FileName</em> 参数指定的文件不存在，则创建一个新文件。</span><span class="sxs-lookup"><span data-stu-id="f7476-p102">Default. Creates a new file if the file specified by the <em>FileName</em> parameter does not already exist.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7476-113"><strong>adSaveCreateOverWrite</strong></span><span class="sxs-lookup"><span data-stu-id="f7476-113"><strong>adSaveCreateOverWrite</strong></span></span></p></td>
<td><p><span data-ttu-id="f7476-114">2</span><span class="sxs-lookup"><span data-stu-id="f7476-114">2</span></span></p></td>
<td><p><span data-ttu-id="f7476-115">如果 <em>Filename</em> 参数指定的文件已存在，则使用当前打开的 <strong>Stream</strong> 对象中的数据覆盖该文件。</span><span class="sxs-lookup"><span data-stu-id="f7476-115">Overwrites the file with the data from the currently open <strong>Stream</strong> object, if the file specified by the <em>Filename</em> parameter already exists.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f7476-116">**ADO/WFC 等效值**</span><span class="sxs-lookup"><span data-stu-id="f7476-116">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="f7476-117">这些常量没有 ADO/WFC 等效值。</span><span class="sxs-lookup"><span data-stu-id="f7476-117">These constants do not have ADO/WFC equivalents.</span></span>

