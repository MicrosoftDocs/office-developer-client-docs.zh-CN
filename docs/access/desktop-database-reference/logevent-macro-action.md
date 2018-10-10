---
title: LogEvent 宏操作
TOCTitle: LogEvent Macro Action
ms:assetid: 3578c725-64b9-385e-ef73-a15cdf751c33
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192460(v=office.15)
ms:contentKeyID: 48544148
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f626dd61782baed2e46aa931891a172fc53c1bde
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467607"
---
# <a name="logevent-macro-action"></a><span data-ttu-id="02a8f-102">LogEvent 宏操作</span><span class="sxs-lookup"><span data-stu-id="02a8f-102">LogEvent Macro Action</span></span>


<span data-ttu-id="02a8f-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="02a8f-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="02a8f-104">**LogEvent** 操作可向 **USysApplicationLog** 系统表中写入信息。</span><span class="sxs-lookup"><span data-stu-id="02a8f-104">The **LogEvent** action writes information to the **USysApplicationLog** system table.</span></span>


> [!NOTE]
> <P><span data-ttu-id="02a8f-105">[!注释] <STRONG>LogEvent</STRONG> 操作仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="02a8f-105">The <STRONG>LogEvent</STRONG> action is available only in Data Macros.</span></span></P>



## <a name="setting"></a><span data-ttu-id="02a8f-106">设置</span><span class="sxs-lookup"><span data-stu-id="02a8f-106">Setting</span></span>

<span data-ttu-id="02a8f-107">**LogEvent** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="02a8f-107">The **LogEvent** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="02a8f-108">参数</span><span class="sxs-lookup"><span data-stu-id="02a8f-108">Argument</span></span></p></th>
<th><p><span data-ttu-id="02a8f-109">是否必需</span><span class="sxs-lookup"><span data-stu-id="02a8f-109">Required</span></span></p></th>
<th><p><span data-ttu-id="02a8f-110">说明</span><span class="sxs-lookup"><span data-stu-id="02a8f-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02a8f-111"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="02a8f-111"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="02a8f-112">否</span><span class="sxs-lookup"><span data-stu-id="02a8f-112">No</span></span></p></td>
<td><p><span data-ttu-id="02a8f-p101">一个用于描述要记录的条件的字符串表达式。该描述不能超过 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="02a8f-p101">A string expression that describes the condition that you want to log. The description cannot exceed 255 characters.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="02a8f-115">注释</span><span class="sxs-lookup"><span data-stu-id="02a8f-115">Remarks</span></span>

<span data-ttu-id="02a8f-p102">**LogEvent** 操作可用于向不应使用 [**RaiseError**](raiseerror-macro-action.md) 操作引发错误的 **USysApplicationLog** 系统表中写入状态信息。例如，您可以记录对特定字段的更改，或使用写入 **USysApplicationLog** 的项来帮助您调试宏。</span><span class="sxs-lookup"><span data-stu-id="02a8f-p102">The **LogEvent** action can be used to write status information to the **USysApplicationLog** system table that does not merit using the **[RaiseError](raiseerror-macro-action.md)** action to throw an error. For example, you could log changes to a specific field, or use the items written to the **USysApplicationLog** to assist you in debugging your macro.</span></span>

<span data-ttu-id="02a8f-118">当您使用**LogEvent**操作写入**USysApplicationLog**表时，**类别**列会自动设置给**用户**。</span><span class="sxs-lookup"><span data-stu-id="02a8f-118">When you use the **LogEvent** action to write to the **USysApplicationLog** table, the **Category** column is automatically set to **User**.</span></span>

<span data-ttu-id="02a8f-119">若要查看 **USysApplicationLog** 表，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="02a8f-119">To see the **USysApplicationLog** table, use the following steps:</span></span>

1.  <span data-ttu-id="02a8f-120">单击 **"文件"** 菜单，然后单击 **"选项"**。</span><span class="sxs-lookup"><span data-stu-id="02a8f-120">Click the **File** menu,and then click **Options**.</span></span>

2.  <span data-ttu-id="02a8f-121">在 **"Access 选项"** 对话框中，单击 **"当前数据库"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="02a8f-121">In the **Access Options** dialog box, click the **Current Database** tab.</span></span>

3.  <span data-ttu-id="02a8f-122">在 **"导航"** 部分，单击 **"导航选项"**。</span><span class="sxs-lookup"><span data-stu-id="02a8f-122">In the **Navigation** section, click **Navigation Options**.</span></span>

4.  <span data-ttu-id="02a8f-123">在 **"导航选项"** 对话框中，单击 **"显示系统对象"**，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="02a8f-123">In the **Navigation Options** dialog box, click **Show System Objects**, and then click **OK**.</span></span>

5.  <span data-ttu-id="02a8f-124">单击 **"确定"** 关闭 **"Access 选项"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="02a8f-124">Click **OK** to dismiss the **Access Options** dialog box.</span></span>

