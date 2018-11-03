---
title: FindNextRecord 宏操作
TOCTitle: FindNextRecord macro action
ms:assetid: 57fb6457-9098-4e81-c693-78ccd262ce0b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194307(v=office.15)
ms:contentKeyID: 48544985
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm89832
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 426bf296345c47abe58e3e6e5057a43a0d43aa21
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25936628"
---
# <a name="findnextrecord-macro-action"></a><span data-ttu-id="2e41d-102">FindNextRecord 宏操作</span><span class="sxs-lookup"><span data-stu-id="2e41d-102">FindNextRecord macro action</span></span>


<span data-ttu-id="2e41d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="2e41d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2e41d-p101">可以使用 **FindNextRecord** 操作查找符合上一个 **FindRecord** 操作指定的条件或与 **"查找和替换"** 对话框（在 **"开始"** 选项卡上单击 **"查找"**）中的值匹配的下一个记录。可以使用 **FindNextRecord** 操作重复搜索记录。例如，您可以在特定客户的所有记录间逐个移动。</span><span class="sxs-lookup"><span data-stu-id="2e41d-p101">You can use the **FindNextRecord** action to find the next record that meets the criteria specified by the previous **FindRecord** action or the value in the **Find and Replace** dialog box (on the **Home** tab, click **Find**). You can use the **FindNextRecord** action to search repeatedly for records. For example, you can move successively through all the records for a specific customer.</span></span>

## <a name="setting"></a><span data-ttu-id="2e41d-107">设置</span><span class="sxs-lookup"><span data-stu-id="2e41d-107">Setting</span></span>

<span data-ttu-id="2e41d-p102">**FindNextRecord** 操作不具有任何参数。 **FindNextRecord** 操作会查找符合 **FindRecord** 操作或 **"查找和替换"** 对话框所设置的条件的下一个记录。 **FindRecord** 操作的参数由 **"查找和替换"** 对话框中的选项共享。</span><span class="sxs-lookup"><span data-stu-id="2e41d-p102">The **FindNextRecord** action doesn't have any arguments. The **FindNextRecord** action finds the next record that meets the criteria set either by the **FindRecord** action or in the **Find and Replace** dialog box. The arguments for the **FindRecord** action are shared with the options in the **Find and Replace** dialog box.</span></span>

<span data-ttu-id="2e41d-p103">若要设置搜索条件，请使用 **FindRecord** 操作。通常的做法是先在宏中输入 **FindRecord** 操作，再使用 **FindNextRecord** 操作查找符合相同条件的后续记录。若要仅在满足特定条件的情况下搜索记录，可以在 **FindNextRecord** 操作的操作行的 **"条件"** 列中输入条件表达式。</span><span class="sxs-lookup"><span data-stu-id="2e41d-p103">To set the search criteria, use the **FindRecord** action. Typically, you enter a **FindRecord** action in a macro and then use the **FindNextRecord** action to find succeeding records that meet the same criteria. To search for records only when a certain condition is met, you can enter a conditional expression in the **Condition** column of the action row for the **FindNextRecord** action.</span></span>

## <a name="remarks"></a><span data-ttu-id="2e41d-114">说明</span><span class="sxs-lookup"><span data-stu-id="2e41d-114">Remarks</span></span>

<span data-ttu-id="2e41d-115">此操作与使用 **"查找和替换"** 对话框中的 **"查找下一个"** 按钮的效果相同。</span><span class="sxs-lookup"><span data-stu-id="2e41d-115">This action has the same effect as using the **Find Next** button in the **Find and Replace** dialog box.</span></span>

> [!NOTE]
> <span data-ttu-id="2e41d-p104">[!注释] 对于表、查询和窗体，虽然 **FindRecord** 操作与 **"开始"** 选项卡上的 **"查找"** 命令相对应，但并不与"代码"窗口中 **"编辑"** 菜单上的 **"查找"** 命令相对应。不能使用 **FindRecord** 或 **FindNextRecord** 操作搜索模块中的文本。</span><span class="sxs-lookup"><span data-stu-id="2e41d-p104">Although the **FindRecord** action corresponds to the **Find** command on the **Home** tab for tables, queries, and forms, it doesn't correspond to the **Find** command on the **Edit** menu in the Code window. You can't use the **FindRecord** action or **FindNextRecord** action to search for text in modules.</span></span>

> [!TIP]
> <span data-ttu-id="2e41d-118">如果您已将**FindRecord**操作**只搜索当前字段**参数设置为**是**，您可能需要使用**GoToControl**操作将焦点移到控件包含使用**之前要搜索的数据FindNextRecord**操作。</span><span class="sxs-lookup"><span data-stu-id="2e41d-118">If you've set the **Only Current Field** argument of the **FindRecord** action to **Yes**, you may need to use the **GoToControl** action to move the focus to the control containing the data you're searching for before you use the **FindNextRecord** action.</span></span>

<span data-ttu-id="2e41d-p105">在执行 **FindNextRecord** 宏操作时，如果当前所选的文本与搜索文本相同，则会从所选文本之后开始在包含该文本的同一字段和同一记录中进行搜索；否则将从当前记录的起始位置开始搜索。这样可以找到单个记录中可能出现的符合相同搜索条件的多个实例。</span><span class="sxs-lookup"><span data-stu-id="2e41d-p105">If the currently selected text is the same as the search text at the time the **FindNextRecord** macro action is carried out, the search begins immediately following the selection, in the same field as the selection, and in the same record. Otherwise, the search begins at the start of the current record. This enables you to find multiple instances of the same search criteria that might appear in a single record.</span></span>

<span data-ttu-id="2e41d-p106">但请注意，如果使用命令按钮运行包含 **FindNextRecord** 操作的宏，则将重复找到符合搜索条件的第一个实例。出现这种情况的原因是，单击命令按钮会将焦点从包含匹配值的字段中移走。这样， **FindNextRecord** 操作将从记录的起始位置开始搜索。为了避免此问题，请使用不会更改焦点的技术运行该宏，例如使用自定义工具栏按钮或在 AutoKeys 宏中定义的组合键。此外，也可以在执行 **FindNextRecord** 操作之前将宏中的焦点设置为包含搜索条件的字段。</span><span class="sxs-lookup"><span data-stu-id="2e41d-p106">However, note that if you use a command button to run a macro containing the **FindNextRecord** action, the first instance of the search criteria will be found repeatedly. This behavior occurs because clicking the command button removes the focus from the field containing the matching value. The **FindNextRecord** action will then begin searching from the start of the record. To avoid this problem, run the macro by using a technique that doesn't change the focus, such as a custom toolbar button or a key combination defined in an AutoKeys macro. Alternatively, set the focus in the macro to the field containing the search criteria before you carry out the **FindNextRecord** action.</span></span>

<span data-ttu-id="2e41d-127">如果您使用的命令按钮运行包含**FindRecord**操作，**查找第一个**参数设置为**否**的宏，也会发生相同的行为。</span><span class="sxs-lookup"><span data-stu-id="2e41d-127">The same behavior also occurs if you use a command button to run a macro containing the **FindRecord** action with the **Find First** argument set to **No**.</span></span>

<span data-ttu-id="2e41d-128">若要在 Visual Basic for Applications 模块中运行 **FindNextRecord** 操作，请使用 **DoCmd** 对象的 **FindNext** 方法。</span><span class="sxs-lookup"><span data-stu-id="2e41d-128">To run the **FindNextRecord** action in a Visual Basic for Applications module, use the **FindNext** method of the **DoCmd** object.</span></span>

