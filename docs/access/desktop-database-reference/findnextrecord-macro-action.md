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
localization_priority: Normal
ms.openlocfilehash: c92a43ce2f4417fde83a544022a90cfca572bf60
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292347"
---
# <a name="findnextrecord-macro-action"></a>FindNextRecord 宏操作


**适用于**：Access 2013、Office 2013

可以使用 **FindNextRecord** 操作查找符合上一个 **FindRecord** 操作指定的条件或与 **"查找和替换"** 对话框（在 **"开始"** 选项卡上单击 **"查找"**）中的值匹配的下一个记录。可以使用 **FindNextRecord** 操作重复搜索记录。例如，您可以在特定客户的所有记录间逐个移动。

## <a name="setting"></a>Setting

**FindNextRecord** 操作不具有任何参数。 **FindNextRecord** 操作会查找符合 **FindRecord** 操作或 **"查找和替换"** 对话框所设置的条件的下一个记录。 **FindRecord** 操作的参数由 **"查找和替换"** 对话框中的选项共享。

若要设置搜索条件，请使用 **FindRecord** 操作。通常的做法是先在宏中输入 **FindRecord** 操作，再使用 **FindNextRecord** 操作查找符合相同条件的后续记录。若要仅在满足特定条件的情况下搜索记录，可以在 **FindNextRecord** 操作的操作行的 **"条件"** 列中输入条件表达式。

## <a name="remarks"></a>注解

此操作与使用 **“查找和替换”** 对话框中的 **“查找下一个”** 按钮的效果相同。

> [!NOTE]
> [!注释] 对于表、查询和窗体，虽然 **FindRecord** 操作与 **"开始"** 选项卡上的 **"查找"** 命令相对应，但并不与"代码"窗口中 **"编辑"** 菜单上的 **"查找"** 命令相对应。不能使用 **FindRecord** 或 **FindNextRecord** 操作搜索模块中的文本。

> [!TIP]
> If you've set the **Only Current Field** argument of the **FindRecord** action to **Yes**, you may need to use the **GoToControl** action to move the focus to the control containing the data you're searching for before you use the **FindNextRecord** action.

在执行 **FindNextRecord** 宏操作时，如果当前所选的文本与搜索文本相同，则会从所选文本之后开始在包含该文本的同一字段和同一记录中进行搜索；否则将从当前记录的起始位置开始搜索。这样可以找到单个记录中可能出现的符合相同搜索条件的多个实例。

但请注意，如果使用命令按钮运行包含 **FindNextRecord** 操作的宏，则将重复找到符合搜索条件的第一个实例。出现这种情况的原因是，单击命令按钮会将焦点从包含匹配值的字段中移走。这样， **FindNextRecord** 操作将从记录的起始位置开始搜索。为了避免此问题，请使用不会更改焦点的技术运行该宏，例如使用自定义工具栏按钮或在 AutoKeys 宏中定义的组合键。此外，也可以在执行 **FindNextRecord** 操作之前将宏中的焦点设置为包含搜索条件的字段。

The same behavior also occurs if you use a command button to run a macro containing the **FindRecord** action with the **Find First** argument set to **No**.

若要在 Visual Basic for Applications 模块中运行 **FindNextRecord** 操作，请使用 **DoCmd** 对象的 **FindNext** 方法。

