---
title: SetField 宏操作
TOCTitle: SetField macro action
ms:assetid: 66bd26e3-e8c3-b9a1-2f16-f29adc44a345
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195227(v=office.15)
ms:contentKeyID: 48545349
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d8ca2315a9a84000aa29b88043e4edea05ffb0ea
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922823"
---
# <a name="setfield-macro-action"></a><span data-ttu-id="0dc66-102">SetField 宏操作</span><span class="sxs-lookup"><span data-stu-id="0dc66-102">SetField macro action</span></span>


<span data-ttu-id="0dc66-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="0dc66-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0dc66-104">**SetField** 操作可用于向字段分配值。</span><span class="sxs-lookup"><span data-stu-id="0dc66-104">The **SetField** action can be used to assign a value to a field.</span></span>


> [!NOTE]
> <P><span data-ttu-id="0dc66-105">[!注释] <STRONG>SetField</STRONG> 操作仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="0dc66-105">The <STRONG>SetField</STRONG> action is available only in Data Macros.</span></span></P>



## <a name="setting"></a><span data-ttu-id="0dc66-106">设置</span><span class="sxs-lookup"><span data-stu-id="0dc66-106">Setting</span></span>

<span data-ttu-id="0dc66-107">下表列出了 **SetField** 操作的相关参数。</span><span class="sxs-lookup"><span data-stu-id="0dc66-107">The **SetField** action has the arguments listed in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0dc66-108">参数</span><span class="sxs-lookup"><span data-stu-id="0dc66-108">Argument</span></span></p></th>
<th><p><span data-ttu-id="0dc66-109">说明</span><span class="sxs-lookup"><span data-stu-id="0dc66-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0dc66-110"><strong>Name</strong></span><span class="sxs-lookup"><span data-stu-id="0dc66-110"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="0dc66-111">一个用于标识字段的字符串。</span><span class="sxs-lookup"><span data-stu-id="0dc66-111">A string that identifies the field.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0dc66-112"><strong>值</strong></span><span class="sxs-lookup"><span data-stu-id="0dc66-112"><strong>Value</strong></span></span></p></td>
<td><p><span data-ttu-id="0dc66-113">一个表达式，指定要分配到的域的值。</span><span class="sxs-lookup"><span data-stu-id="0dc66-113">An expression that specifies the value to assign to the field.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="0dc66-114">注释</span><span class="sxs-lookup"><span data-stu-id="0dc66-114">Remarks</span></span>

<span data-ttu-id="0dc66-115">无法在 [**CreateRecord**](createrecord-data-block.md) 或 [**EditRecord**](editrecord-data-block.md) 数据块外部使用 **SetField** 操作。</span><span class="sxs-lookup"><span data-stu-id="0dc66-115">The **SetField** action cannot be used outside of an **[CreateRecord](createrecord-data-block.md)** or **[EditRecord](editrecord-data-block.md)** data block.</span></span>

