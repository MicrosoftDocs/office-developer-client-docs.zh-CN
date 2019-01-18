---
title: SaveOptionsEnum （访问桌面数据库参考 （英文）
TOCTitle: SaveOptionsEnum
ms:assetid: 2a4e4c7a-6331-7270-0514-cc549c721ffd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249053(v=office.15)
ms:contentKeyID: 48543906
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 77a617dc54d8acd145648d926e10cf7c9a3cf252
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28705993"
---
# <a name="saveoptionsenum"></a><span data-ttu-id="69bdc-102">SaveOptionsEnum</span><span class="sxs-lookup"><span data-stu-id="69bdc-102">SaveOptionsEnum</span></span>

<span data-ttu-id="69bdc-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="69bdc-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="69bdc-p101">指定当从 [Stream](stream-object-ado.md) 对象进行保存时，应创建文件还是覆盖文件。可以使用 AND 运算符来组合使用这些值。</span><span class="sxs-lookup"><span data-stu-id="69bdc-p101">Specifies whether a file should be created or overwritten when saving from a [Stream](stream-object-ado.md) object. The values can be combined with an AND operator.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="69bdc-106">常量</span><span class="sxs-lookup"><span data-stu-id="69bdc-106">Constant</span></span></p></th>
<th><p><span data-ttu-id="69bdc-107">值</span><span class="sxs-lookup"><span data-stu-id="69bdc-107">Value</span></span></p></th>
<th><p><span data-ttu-id="69bdc-108">说明</span><span class="sxs-lookup"><span data-stu-id="69bdc-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69bdc-109"><strong>adSaveCreateNotExist</strong></span><span class="sxs-lookup"><span data-stu-id="69bdc-109"><strong>adSaveCreateNotExist</strong></span></span></p></td>
<td><p><span data-ttu-id="69bdc-110">1</span><span class="sxs-lookup"><span data-stu-id="69bdc-110">1</span></span></p></td>
<td><p><span data-ttu-id="69bdc-p102">默认值。指示如果 <em>FileName</em> 参数指定的文件不存在，则创建一个新文件。</span><span class="sxs-lookup"><span data-stu-id="69bdc-p102">Default. Creates a new file if the file specified by the <em>FileName</em> parameter does not already exist.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bdc-113"><strong>adSaveCreateOverWrite</strong></span><span class="sxs-lookup"><span data-stu-id="69bdc-113"><strong>adSaveCreateOverWrite</strong></span></span></p></td>
<td><p><span data-ttu-id="69bdc-114">2</span><span class="sxs-lookup"><span data-stu-id="69bdc-114">2</span></span></p></td>
<td><p><span data-ttu-id="69bdc-115">如果 <em>Filename</em> 参数指定的文件已存在，则使用当前打开的 <strong>Stream</strong> 对象中的数据覆盖该文件。</span><span class="sxs-lookup"><span data-stu-id="69bdc-115">Overwrites the file with the data from the currently open <strong>Stream</strong> object, if the file specified by the <em>Filename</em> parameter already exists.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="69bdc-116">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="69bdc-116">ADO/WFC equivalent</span></span>

<span data-ttu-id="69bdc-117">这些常量没有 ADO/WFC 等效值。</span><span class="sxs-lookup"><span data-stu-id="69bdc-117">These constants do not have ADO/WFC equivalents.</span></span>

