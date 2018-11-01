---
title: RunMenuCommand 宏操作
TOCTitle: RunMenuCommand Macro Action
ms:assetid: cc4a4f72-0c73-91b7-8cec-6cbcda7e5b1c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834420(v=office.15)
ms:contentKeyID: 48547735
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm6446
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 372803779767ea6fdc12b4e10b5dde231ce101fc
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25875510"
---
# <a name="runmenucommand-macro-action"></a><span data-ttu-id="4478a-102">RunMenuCommand 宏操作</span><span class="sxs-lookup"><span data-stu-id="4478a-102">RunMenuCommand Macro Action</span></span>


<span data-ttu-id="4478a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4478a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4478a-104">可以使用 **RunMenuCommand** 操作运行内置的 Microsoft Access 命令。</span><span class="sxs-lookup"><span data-stu-id="4478a-104">You can use the **RunMenuCommand** action to run a built-in Microsoft Access command.</span></span>

## <a name="setting"></a><span data-ttu-id="4478a-105">设置</span><span class="sxs-lookup"><span data-stu-id="4478a-105">Setting</span></span>

<span data-ttu-id="4478a-106">**RunMenuCommand** 操作具有以下操作参数。</span><span class="sxs-lookup"><span data-stu-id="4478a-106">The **RunMenuCommand** action has the following action argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4478a-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="4478a-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="4478a-108">说明</span><span class="sxs-lookup"><span data-stu-id="4478a-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4478a-109"><strong>Command</strong></span><span class="sxs-lookup"><span data-stu-id="4478a-109"><strong>Command</strong></span></span></p></td>
<td><p><span data-ttu-id="4478a-p101">要运行的命令的名称。<strong>“命令”</strong>框按照字母顺序显示 Access 中可用的内置命令。这是一个必选参数。</span><span class="sxs-lookup"><span data-stu-id="4478a-p101">The name of the command you want to run. The <strong>Command</strong> box shows the available built-in commands in Access, in alphabetical order. This is a required argument.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="4478a-113">说明</span><span class="sxs-lookup"><span data-stu-id="4478a-113">Remarks</span></span>

<span data-ttu-id="4478a-114">可以使用 **RunMenuCommand** 操作运行自定义菜单栏、全局菜单栏、自定义快捷菜单或全局快捷菜单中的 Access 命令。</span><span class="sxs-lookup"><span data-stu-id="4478a-114">You can use the **RunMenuCommand** action to run an Access command from a custom menu bar, global menu bar, custom shortcut menu, or global shortcut menu.</span></span>

<span data-ttu-id="4478a-115">可以在具有条件表达式的宏内使用 **RunMenuCommand** 操作，以便根据某些条件运行命令。</span><span class="sxs-lookup"><span data-stu-id="4478a-115">You can use the **RunMenuCommand** action in a macro with conditional expressions to run a command depending on certain conditions.</span></span>


> [!NOTE]
> <P><span data-ttu-id="4478a-116">单击<STRONG>文件</STRONG>选项卡，然后单击<STRONG>最近</STRONG>显示最近使用过的数据库。</span><span class="sxs-lookup"><span data-stu-id="4478a-116">Clicking the <STRONG>File</STRONG> tab and then clicking <STRONG>Recent</STRONG> shows the most recently used databases.</span></span> <span data-ttu-id="4478a-117">您可以单击其中一个数据库，而不是单击<STRONG>打开</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="4478a-117">You can click one of these databases instead of clicking <STRONG>Open</STRONG>.</span></span> <span data-ttu-id="4478a-118">这些数据库项不显示在下拉列表框中的<STRONG>命令</STRONG>参数，并且在宏中使用<STRONG>RunMenuCommand</STRONG>操作不可用。</span><span class="sxs-lookup"><span data-stu-id="4478a-118">These database items don't appear in the drop-down list box for the <STRONG>Command</STRONG> argument, and aren't available by using the <STRONG>RunMenuCommand</STRONG> action in a macro.</span></span></P>



<span data-ttu-id="4478a-119">从以前版本的 Access 转换 Access 数据库时，某些命令可能不再可用。</span><span class="sxs-lookup"><span data-stu-id="4478a-119">When you convert an Access database from a previous version of Access, some commands may no longer be available.</span></span> <span data-ttu-id="4478a-120">命令可能已重命名，移动到不同的菜单上，或可能不再在 Access 中可用。</span><span class="sxs-lookup"><span data-stu-id="4478a-120">A command may have been renamed, moved to a different menu, or may no longer be available in Access.</span></span> <span data-ttu-id="4478a-121">此类命令的**DoMenuItem**操作无法转换为**RunMenuCommand**操作。</span><span class="sxs-lookup"><span data-stu-id="4478a-121">The **DoMenuItem** actions for such commands can't be converted to **RunMenuCommand** actions.</span></span> <span data-ttu-id="4478a-122">当打开该宏时，Access 将显示空白**命令**参数此类命令的**RunMenuCommand**操作。</span><span class="sxs-lookup"><span data-stu-id="4478a-122">When you open the macro, Access will display a **RunMenuCommand** action with a blank **Command** argument for such commands.</span></span> <span data-ttu-id="4478a-123">您必须编辑该宏，并输入有效的命令的参数，或删除**RunMenuCommand**操作。</span><span class="sxs-lookup"><span data-stu-id="4478a-123">You must edit the macro and enter a valid command argument, or delete the **RunMenuCommand** action.</span></span>

<span data-ttu-id="4478a-p104">若要在 Visual Basic for Applications (VBA) 模块中运行 **RunMenuCommand** 操作，请使用 **Application** 对象的 **RunCommand** 方法。（此方法等效于 **DoCmd** 对象的 **RunCommand** 方法。）</span><span class="sxs-lookup"><span data-stu-id="4478a-p104">To run the **RunMenuCommand** action in a Visual Basic for Applications (VBA) module, use the **RunCommand** method of the **Application** object. (This is equivalent to the **RunCommand** method of the **DoCmd** object.)</span></span>

