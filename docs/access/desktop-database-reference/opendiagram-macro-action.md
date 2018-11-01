---
title: OpenDiagram 宏操作
TOCTitle: OpenDiagram Macro Action
ms:assetid: 408e7224-02bb-335a-b1b9-cbccbf6e36ec
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192875(v=office.15)
ms:contentKeyID: 48544427
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm154095
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 3118c2a6b85d400b4b797c4b9b711e5f5a512c62
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25869237"
---
# <a name="opendiagram-macro-action"></a><span data-ttu-id="c455a-102">OpenDiagram 宏操作</span><span class="sxs-lookup"><span data-stu-id="c455a-102">OpenDiagram Macro Action</span></span>


<span data-ttu-id="c455a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c455a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c455a-104">在 Access 项目中，可以使用 **OpenDiagram** 操作在设计视图中打开数据库图表。</span><span class="sxs-lookup"><span data-stu-id="c455a-104">In an Access project, you can use the **OpenDiagram** action to open a database diagram in Design view.</span></span>


> [!NOTE]
> <P><span data-ttu-id="c455a-p101">[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</span><span class="sxs-lookup"><span data-stu-id="c455a-p101">This action will not be allowed if the database is not trusted. For more information about enabling macros, see the links in the See Also section of this article.</span></span></P>



## <a name="setting"></a><span data-ttu-id="c455a-107">设置</span><span class="sxs-lookup"><span data-stu-id="c455a-107">Setting</span></span>

<span data-ttu-id="c455a-108">**OpenDiagram** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="c455a-108">The **OpenDiagram** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c455a-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="c455a-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="c455a-110">说明</span><span class="sxs-lookup"><span data-stu-id="c455a-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c455a-111"><strong>图表名称</strong></span><span class="sxs-lookup"><span data-stu-id="c455a-111"><strong>Diagram Name</strong></span></span></p></td>
<td><p><span data-ttu-id="c455a-112">要打开的数据库图表的名称。</span><span class="sxs-lookup"><span data-stu-id="c455a-112">The name of the database diagram to open.</span></span> <span data-ttu-id="c455a-113">宏生成器窗格的<strong>图表名称</strong>框在<strong>操作参数</strong>部分中显示当前数据库中的所有数据库图表。</span><span class="sxs-lookup"><span data-stu-id="c455a-113">The <strong>Diagram Name</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane shows all database diagrams in the current database.</span></span> <span data-ttu-id="c455a-114">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="c455a-114">This is a required argument.</span></span> <span data-ttu-id="c455a-115">如果在类库数据库中运行包含 <strong>OpenDiagram</strong> 操作的宏，Microsoft Access 将先在该类库数据库中查找具有此名称的图表，然后再在当前数据库中查找。</span><span class="sxs-lookup"><span data-stu-id="c455a-115">If you run a macro containing the <strong>OpenDiagram</strong> action in a library database, Microsoft Access first looks for the diagram with this name in the library database, and then in the current database.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="c455a-116">说明</span><span class="sxs-lookup"><span data-stu-id="c455a-116">Remarks</span></span>

<span data-ttu-id="c455a-117">此操作类似于在导航窗格中双击数据库图表，或在导航窗格中右键单击数据库图表并单击 **"设计视图"**。</span><span class="sxs-lookup"><span data-stu-id="c455a-117">This action is similar to double-clicking a database diagram in the Navigation Pane, or right-clicking the database diagram in the Navigation Pane and then clicking **Design View**.</span></span>


> [!TIP]
> <P><span data-ttu-id="c455a-p103">[!提示] 您可以将数据库图表从导航窗格拖至某个宏操作行。这会自动创建在设计视图中打开该数据库图表的 <STRONG>OpenDiagram</STRONG> 操作。</span><span class="sxs-lookup"><span data-stu-id="c455a-p103">You can drag a database diagram from the Navigation Pane to a macro action row. This automatically creates an <STRONG>OpenDiagram</STRONG> action that opens the database diagram in Design view.</span></span></P>



<span data-ttu-id="c455a-120">要在 Visual Basic for Applications (VBA) 模块中运行 **OpenDiagram** 操作，请使用 **DoCmd** 对象的 **OpenDiagram** 方法。</span><span class="sxs-lookup"><span data-stu-id="c455a-120">To run the **OpenDiagram** action in a Visual Basic for Applications (VBA) module, use the **OpenDiagram** method of the **DoCmd** object.</span></span>

