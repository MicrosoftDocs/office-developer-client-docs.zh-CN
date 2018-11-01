---
title: SelectObject 宏操作
TOCTitle: SelectObject Macro Action
ms:assetid: a90539a0-c5a0-e997-9c25-e0972d28f2a6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821420(v=office.15)
ms:contentKeyID: 48546914
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm41840
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 655b5c9273e84be3365116c2e7b93c657c0d732f
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25884056"
---
# <a name="selectobject-macro-action"></a><span data-ttu-id="374bc-102">SelectObject 宏操作</span><span class="sxs-lookup"><span data-stu-id="374bc-102">SelectObject Macro Action</span></span>


<span data-ttu-id="374bc-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="374bc-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="374bc-104">可以使用 **SelectObject** 操作选择指定的数据库对象。</span><span class="sxs-lookup"><span data-stu-id="374bc-104">You can use the **SelectObject** action to select a specified database object.</span></span>

## <a name="setting"></a><span data-ttu-id="374bc-105">设置</span><span class="sxs-lookup"><span data-stu-id="374bc-105">Setting</span></span>

<span data-ttu-id="374bc-106">**SelectObject** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="374bc-106">The **SelectObject** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="374bc-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="374bc-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="374bc-108">说明</span><span class="sxs-lookup"><span data-stu-id="374bc-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="374bc-109"><strong>对象类型</strong></span><span class="sxs-lookup"><span data-stu-id="374bc-109"><strong>Object Type</strong></span></span></p></td>
<td><p><span data-ttu-id="374bc-p101">要选择的数据库对象的类型。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“对象类型”</strong>框中单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“报表”</strong>、<strong>“宏”</strong>、<strong>“模块”</strong>、<strong>“数据访问页”</strong>、<strong>“服务器视图”</strong>、<strong>“图表”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。这是一个必选参数。</span><span class="sxs-lookup"><span data-stu-id="374bc-p101">The type of database object to select. Click <strong>Table</strong>, <strong>Query</strong>, <strong>Form</strong>, <strong>Report</strong>, <strong>Macro</strong>, <strong>Module</strong>, <strong>Data Access Page</strong>, <strong>Server View</strong>, <strong>Diagram</strong>, <strong>Stored Procedure</strong>, or <strong>Function</strong> in the <strong>Object Type</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. This is a required argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="374bc-113"><strong>对象名称</strong></span><span class="sxs-lookup"><span data-stu-id="374bc-113"><strong>Object Name</strong></span></span></p></td>
<td><p><span data-ttu-id="374bc-114">要选择的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="374bc-114">The name of the object to select.</span></span> <span data-ttu-id="374bc-115"><strong>对象名称</strong>框中显示<strong>对象类型</strong>参数所选类型的数据库中的所有对象。</span><span class="sxs-lookup"><span data-stu-id="374bc-115">The <strong>Object Name</strong> box shows all objects in the database of the type selected by the <strong>Object Type</strong> argument.</span></span> <span data-ttu-id="374bc-116">这是一个必需的参数，除非您将在导航窗格中参数设置为<strong>是</strong>。</span><span class="sxs-lookup"><span data-stu-id="374bc-116">This is a required argument, unless you set the In Navigation Pane argument to <strong>Yes</strong>.</span></span></p>

> [!NOTE]
> <P><span data-ttu-id="374bc-117"><STRONG>“服务器视图”</STRONG>、<STRONG>“图表”</STRONG>或<STRONG>“存储过程”</STRONG>对象的对象名称不会显示在 Microsoft Access 项目 (.adp) 的<STRONG>“对象名称”</STRONG>框中。</span><span class="sxs-lookup"><span data-stu-id="374bc-117">The object names for <STRONG>Server View</STRONG>, <STRONG>Diagram</STRONG>, or <STRONG>Stored Procedure</STRONG> objects are not displayed in the <STRONG>Object Name</STRONG> box of an Access project (.adp).</span></span></P>


<p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="374bc-118"><strong>在导航窗格中</strong></span><span class="sxs-lookup"><span data-stu-id="374bc-118"><strong>In Navigation Pane</strong></span></span></p></td>
<td><p><span data-ttu-id="374bc-p103">指定 Microsoft Access 是否选择导航窗格中的对象。请单击<strong>“是”</strong>（选择导航窗格中的对象）或<strong>“否”</strong>（不选择导航窗格中的对象）。默认值为<strong>“否”</strong>。</span><span class="sxs-lookup"><span data-stu-id="374bc-p103">Specifies whether Microsoft Access selects the object in the Navigation Pane. Click <strong>Yes</strong> (to select the object in the Navigation Pane) or <strong>No</strong> (not to select the object in the Navigation Pane). The default is <strong>No</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="374bc-122">说明</span><span class="sxs-lookup"><span data-stu-id="374bc-122">Remarks</span></span>

<span data-ttu-id="374bc-123">**SelectObject**操作适用于可接收焦点任何访问对象。</span><span class="sxs-lookup"><span data-stu-id="374bc-123">The **SelectObject** action works with any Access object that can receive the focus.</span></span> <span data-ttu-id="374bc-124">此操作使指定的对象获得焦点，显示对象如果它处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="374bc-124">This action gives the specified object the focus and shows the object if it's hidden.</span></span> <span data-ttu-id="374bc-125">如果对象是窗体， **SelectObject**操作将窗体的**Visible**属性设置为**是**，并让窗体返回其窗体属性 （例如，为模式或弹出式窗体） 设置的模式。</span><span class="sxs-lookup"><span data-stu-id="374bc-125">If the object is a form, the **SelectObject** action sets the form's **Visible** property to **Yes** and returns the form to the mode set by its form properties (for example, as a modal or pop-up form).</span></span>

<span data-ttu-id="374bc-126">如果在一个其他 Access 窗口中，该对象未打开，您可以通过**在导航窗格中**参数设置为**是**导航窗格中选择它。</span><span class="sxs-lookup"><span data-stu-id="374bc-126">If the object isn't open in one of the other Access windows, you can select it in the Navigation Pane by setting the **In Navigation Pane** argument to **Yes**.</span></span> <span data-ttu-id="374bc-127">如果将**在导航窗格中**参数设置为**否**，，当您尝试选择未打开对象时，但未出现错误消息。</span><span class="sxs-lookup"><span data-stu-id="374bc-127">If you set the **In Navigation Pane** argument to **No**, an error message appears when you try to select an object that isn't open.</span></span>

<span data-ttu-id="374bc-p106">通常，您可能会使用此操作来选择要对其执行其他操作的对象。例如，如果您将 Access 配置为使用重叠窗口，而不是使用选项卡式文档，您可能需要还原已经最小化的对象（使用 **RestoreWindow** 操作）或最大化包含您要使用的对象的窗口（使用 **MaximizeWindow** 操作）。</span><span class="sxs-lookup"><span data-stu-id="374bc-p106">Often, you might use this action to select an object on which you want to perform additional actions. For example, if you have Access configured to use overlapping windows instead of tabbed documents, you may want to restore an object that has been minimized (by using the **RestoreWindow** action) or maximize a window that contains an object you want to work with (by using the **MaximizeWindow** action).</span></span>

<span data-ttu-id="374bc-p107">如果您选择了窗体，则可以使用 **GoToControl** 、 **GoToRecord** 和 **GoToPage** 操作移动至窗体上的特定区域。 **GoToRecord** 操作也适用于数据表。</span><span class="sxs-lookup"><span data-stu-id="374bc-p107">If you select a form, you can use the **GoToControl**, **GoToRecord**, and **GoToPage** actions to move to specific areas on the form. The **GoToRecord** action also works for datasheets.</span></span>

<span data-ttu-id="374bc-132">要在 Visual Basic for Applications (VBA) 模块中运行 **SelectObject** 操作，请使用 **DoCmd** 对象的 **SelectObject** 方法。</span><span class="sxs-lookup"><span data-stu-id="374bc-132">To run the **SelectObject** action in a Visual Basic for Applications (VBA) module, use the **SelectObject** method of the **DoCmd** object.</span></span>

