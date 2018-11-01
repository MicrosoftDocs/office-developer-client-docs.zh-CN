---
title: QuitAccess 宏操作
TOCTitle: QuitAccess Macro Action
ms:assetid: af063f65-d3b1-fa9a-4bc1-04b0d21d62b9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821759(v=office.15)
ms:contentKeyID: 48547089
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm96777
f1_categories:
- Office.Version=v15
ms.openlocfilehash: d26f8d32e0df350c52ea22dfec44ac7a24c9ecc9
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870749"
---
# <a name="quitaccess-macro-action"></a><span data-ttu-id="10b42-102">QuitAccess 宏操作</span><span class="sxs-lookup"><span data-stu-id="10b42-102">QuitAccess Macro Action</span></span>


<span data-ttu-id="10b42-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="10b42-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="10b42-p101">可以使用 **QuitAccess** 操作退出 Microsoft Access。 **QuitAccess** 操作还可以指定在退出 Access 之前用于保存数据库对象的若干选项之一。</span><span class="sxs-lookup"><span data-stu-id="10b42-p101">You can use the **QuitAccess** action to exit Microsoft Access. The **QuitAccess** action can also specify one of several options for saving database objects prior to exiting Access.</span></span>


> [!NOTE]
> <P><span data-ttu-id="10b42-p102">[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</span><span class="sxs-lookup"><span data-stu-id="10b42-p102">This action will not be allowed if the database is not trusted. For more information about enabling macros, see the links in the See Also section of this article.</span></span></P>



## <a name="setting"></a><span data-ttu-id="10b42-108">设置</span><span class="sxs-lookup"><span data-stu-id="10b42-108">Setting</span></span>

<span data-ttu-id="10b42-109">**QuitAccess** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="10b42-109">The **QuitAccess** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="10b42-110">操作参数</span><span class="sxs-lookup"><span data-stu-id="10b42-110">Action argument</span></span></p></th>
<th><p><span data-ttu-id="10b42-111">说明</span><span class="sxs-lookup"><span data-stu-id="10b42-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10b42-112"><strong>Options</strong></span><span class="sxs-lookup"><span data-stu-id="10b42-112"><strong>Options</strong></span></span></p></td>
<td><p><span data-ttu-id="10b42-p103">指定在退出 Access 时未保存的对象会出现什么情况。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“选项”</strong>对话框中单击<strong>“提示”</strong>（显示询问是否保存每个对象的对话框）、<strong>“全部保存”</strong>（直接保存所有对象而不使用对话框提示）或<strong>“退出”</strong>（退出而不保存任何对象）。默认值为<strong>“全部保存”</strong>。</span><span class="sxs-lookup"><span data-stu-id="10b42-p103">Specifies what happens to unsaved objects when you quit Access. Click <strong>Prompt</strong> (to display dialog boxes that ask whether to save each object), <strong>Save All</strong> (to save all objects without prompting by dialog boxes), or <strong>Exit</strong> (to quit without saving any objects) in the <strong>Options</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. The default is <strong>Save All</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="10b42-116">说明</span><span class="sxs-lookup"><span data-stu-id="10b42-116">Remarks</span></span>

<span data-ttu-id="10b42-117">Access 不运行宏的 **QuitAccess** 操作后的任何操作。</span><span class="sxs-lookup"><span data-stu-id="10b42-117">Access doesn't run any actions that follow the **QuitAccess** action in a macro.</span></span>

<span data-ttu-id="10b42-118">您可以使用此操作退出 Access 不提示**保存**对话框通过使用窗体上的自定义菜单命令或按钮。</span><span class="sxs-lookup"><span data-stu-id="10b42-118">You can use this action to quit Access without prompts from **Save** dialog boxes by using a custom menu command or a button on a form.</span></span> <span data-ttu-id="10b42-119">例如，您可能必须使用您的自定义工作区中显示的对象的主窗体。</span><span class="sxs-lookup"><span data-stu-id="10b42-119">For example, you might have a master form that you use to display the objects in your custom workspace.</span></span> <span data-ttu-id="10b42-120">此窗体无法有运行的宏的**QuitAccess**操作包含**选项**参数设置为**全部保存\*\*\*\*退出**按钮。</span><span class="sxs-lookup"><span data-stu-id="10b42-120">This form could have a **Quit** button that runs a macro containing the **QuitAccess** action with the **Options** argument set to **Save All**.</span></span>

<span data-ttu-id="10b42-121">此操作具有相同的效果，然后单击**退出**打开**文件**选项卡。</span><span class="sxs-lookup"><span data-stu-id="10b42-121">This action has the same effect as clicking the **File** tab and then clicking **Exit**.</span></span> <span data-ttu-id="10b42-122">如果您有任何未保存的对象，当您单击此命令时，显示对话框是显示使用**提示**的**QuitAccess**操作在**Options**参数时的相同。</span><span class="sxs-lookup"><span data-stu-id="10b42-122">If you have any unsaved objects when you click this command, the dialog boxes that appear are the same as those displayed when you use **Prompt** for the **Options** argument of the **QuitAccess** action.</span></span>

<span data-ttu-id="10b42-123">可以使用宏中的 **SaveObject** 操作保存指定的对象，而不必退出 Access 或者关闭该对象。</span><span class="sxs-lookup"><span data-stu-id="10b42-123">You can use the **SaveObject** action in a macro to save a specified object without having to quit Access or close the object.</span></span>

<span data-ttu-id="10b42-124">若要在 Visual Basic for Applications (VBA) 模块中运行 **QuitAccess** 操作，请使用 **DoCmd** 对象的 **Quit** 方法。</span><span class="sxs-lookup"><span data-stu-id="10b42-124">To run the **QuitAccess** action in a Visual Basic for Applications (VBA) module, use the **Quit** method of the **DoCmd** object.</span></span>

