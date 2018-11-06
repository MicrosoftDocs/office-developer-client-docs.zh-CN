---
title: LogEvent 宏操作
TOCTitle: LogEvent macro action
ms:assetid: 3578c725-64b9-385e-ef73-a15cdf751c33
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192460(v=office.15)
ms:contentKeyID: 48544148
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: edc2fcaa72f6bfb912708948903aa09b25447580
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998168"
---
# <a name="logevent-macro-action"></a><span data-ttu-id="b83fd-102">LogEvent 宏操作</span><span class="sxs-lookup"><span data-stu-id="b83fd-102">LogEvent macro action</span></span>

<span data-ttu-id="b83fd-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b83fd-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b83fd-104">**LogEvent** 操作可向 **USysApplicationLog** 系统表中写入信息。</span><span class="sxs-lookup"><span data-stu-id="b83fd-104">The **LogEvent** action writes information to the **USysApplicationLog** system table.</span></span>

> [!NOTE]
> <span data-ttu-id="b83fd-105">[!注释] **LogEvent** 操作仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="b83fd-105">The **LogEvent** action is available only in Data Macros.</span></span>

## <a name="setting"></a><span data-ttu-id="b83fd-106">设置</span><span class="sxs-lookup"><span data-stu-id="b83fd-106">Setting</span></span>

<span data-ttu-id="b83fd-107">**LogEvent** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="b83fd-107">The **LogEvent** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b83fd-108">参数</span><span class="sxs-lookup"><span data-stu-id="b83fd-108">Argument</span></span></p></th>
<th><p><span data-ttu-id="b83fd-109">是否必需</span><span class="sxs-lookup"><span data-stu-id="b83fd-109">Required</span></span></p></th>
<th><p><span data-ttu-id="b83fd-110">说明</span><span class="sxs-lookup"><span data-stu-id="b83fd-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b83fd-111"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="b83fd-111"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="b83fd-112">否</span><span class="sxs-lookup"><span data-stu-id="b83fd-112">No</span></span></p></td>
<td><p><span data-ttu-id="b83fd-p101">一个用于描述要记录的条件的字符串表达式。该描述不能超过 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="b83fd-p101">A string expression that describes the condition that you want to log. The description cannot exceed 255 characters.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="remarks"></a><span data-ttu-id="b83fd-115">注释</span><span class="sxs-lookup"><span data-stu-id="b83fd-115">Remarks</span></span>

<span data-ttu-id="b83fd-p102">**LogEvent** 操作可用于向不应使用 [**RaiseError**](raiseerror-macro-action.md) 操作引发错误的 **USysApplicationLog** 系统表中写入状态信息。例如，您可以记录对特定字段的更改，或使用写入 **USysApplicationLog** 的项来帮助您调试宏。</span><span class="sxs-lookup"><span data-stu-id="b83fd-p102">The **LogEvent** action can be used to write status information to the **USysApplicationLog** system table that does not merit using the **[RaiseError](raiseerror-macro-action.md)** action to throw an error. For example, you could log changes to a specific field, or use the items written to the **USysApplicationLog** to assist you in debugging your macro.</span></span>

<span data-ttu-id="b83fd-118">当您使用**LogEvent**操作写入**USysApplicationLog**表时，**类别**列会自动设置给**用户**。</span><span class="sxs-lookup"><span data-stu-id="b83fd-118">When you use the **LogEvent** action to write to the **USysApplicationLog** table, the **Category** column is automatically set to **User**.</span></span>

<span data-ttu-id="b83fd-119">若要查看 **USysApplicationLog** 表，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b83fd-119">To see the **USysApplicationLog** table, use the following steps:</span></span>

1.  <span data-ttu-id="b83fd-120">单击 **"文件"** 菜单，然后单击 **"选项"**。</span><span class="sxs-lookup"><span data-stu-id="b83fd-120">Click the **File** menu,and then click **Options**.</span></span>

2.  <span data-ttu-id="b83fd-121">在 **"Access 选项"** 对话框中，单击 **"当前数据库"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b83fd-121">In the **Access Options** dialog box, click the **Current Database** tab.</span></span>

3.  <span data-ttu-id="b83fd-122">在 **"导航"** 部分，单击 **"导航选项"**。</span><span class="sxs-lookup"><span data-stu-id="b83fd-122">In the **Navigation** section, click **Navigation Options**.</span></span>

4.  <span data-ttu-id="b83fd-123">在 **"导航选项"** 对话框中，单击 **"显示系统对象"**，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="b83fd-123">In the **Navigation Options** dialog box, click **Show System Objects**, and then click **OK**.</span></span>

5.  <span data-ttu-id="b83fd-124">单击 **"确定"** 关闭 **"Access 选项"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="b83fd-124">Click **OK** to dismiss the **Access Options** dialog box.</span></span>

