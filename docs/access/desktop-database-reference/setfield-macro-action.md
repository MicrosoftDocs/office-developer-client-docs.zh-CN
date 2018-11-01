---
title: SetField 宏操作
TOCTitle: SetField Macro Action
ms:assetid: 66bd26e3-e8c3-b9a1-2f16-f29adc44a345
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195227(v=office.15)
ms:contentKeyID: 48545349
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1be405402c5f410c892c2dd8904133e09039351a
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25869502"
---
# <a name="setfield-macro-action"></a><span data-ttu-id="b9c0a-102">SetField 宏操作</span><span class="sxs-lookup"><span data-stu-id="b9c0a-102">SetField Macro Action</span></span>


<span data-ttu-id="b9c0a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b9c0a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b9c0a-104">**SetField** 操作可用于向字段分配值。</span><span class="sxs-lookup"><span data-stu-id="b9c0a-104">The **SetField** action can be used to assign a value to a field.</span></span>


> [!NOTE]
> <P><span data-ttu-id="b9c0a-105">[!注释] <STRONG>SetField</STRONG> 操作仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="b9c0a-105">The <STRONG>SetField</STRONG> action is available only in Data Macros.</span></span></P>



## <a name="setting"></a><span data-ttu-id="b9c0a-106">设置</span><span class="sxs-lookup"><span data-stu-id="b9c0a-106">Setting</span></span>

<span data-ttu-id="b9c0a-107">下表列出了 **SetField** 操作的相关参数。</span><span class="sxs-lookup"><span data-stu-id="b9c0a-107">The **SetField** action has the arguments listed in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b9c0a-108">参数</span><span class="sxs-lookup"><span data-stu-id="b9c0a-108">Argument</span></span></p></th>
<th><p><span data-ttu-id="b9c0a-109">说明</span><span class="sxs-lookup"><span data-stu-id="b9c0a-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9c0a-110"><strong>Name</strong></span><span class="sxs-lookup"><span data-stu-id="b9c0a-110"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="b9c0a-111">一个用于标识字段的字符串。</span><span class="sxs-lookup"><span data-stu-id="b9c0a-111">A string that identifies the field.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9c0a-112"><strong>值</strong></span><span class="sxs-lookup"><span data-stu-id="b9c0a-112"><strong>Value</strong></span></span></p></td>
<td><p><span data-ttu-id="b9c0a-113">一个表达式，指定要分配到的域的值。</span><span class="sxs-lookup"><span data-stu-id="b9c0a-113">An expression that specifies the value to assign to the field.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="b9c0a-114">注释</span><span class="sxs-lookup"><span data-stu-id="b9c0a-114">Remarks</span></span>

<span data-ttu-id="b9c0a-115">无法在 [**CreateRecord**](createrecord-data-block.md) 或 [**EditRecord**](editrecord-data-block.md) 数据块外部使用 **SetField** 操作。</span><span class="sxs-lookup"><span data-stu-id="b9c0a-115">The **SetField** action cannot be used outside of an **[CreateRecord](createrecord-data-block.md)** or **[EditRecord](editrecord-data-block.md)** data block.</span></span>

