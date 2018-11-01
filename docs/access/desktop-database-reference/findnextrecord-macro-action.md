---
title: FindNextRecord 宏操作
TOCTitle: FindNextRecord Macro Action
ms:assetid: 57fb6457-9098-4e81-c693-78ccd262ce0b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194307(v=office.15)
ms:contentKeyID: 48544985
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm89832
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 05dec445360d5c42636880982e27e0abd46d048e
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25883650"
---
# <a name="findnextrecord-macro-action"></a>FindNextRecord 宏操作


**适用于**： Access 2013、 Office 2013

可以使用 **FindNextRecord** 操作查找符合上一个 **FindRecord** 操作指定的条件或与 **"查找和替换"** 对话框（在 **"开始"** 选项卡上单击 **"查找"**）中的值匹配的下一个记录。可以使用 **FindNextRecord** 操作重复搜索记录。例如，您可以在特定客户的所有记录间逐个移动。

## <a name="setting"></a>设置

**FindNextRecord** 操作不具有任何参数。 **FindNextRecord** 操作会查找符合 **FindRecord** 操作或 **"查找和替换"** 对话框所设置的条件的下一个记录。 **FindRecord** 操作的参数由 **"查找和替换"** 对话框中的选项共享。

若要设置搜索条件，请使用 **FindRecord** 操作。通常的做法是先在宏中输入 **FindRecord** 操作，再使用 **FindNextRecord** 操作查找符合相同条件的后续记录。若要仅在满足特定条件的情况下搜索记录，可以在 **FindNextRecord** 操作的操作行的 **"条件"** 列中输入条件表达式。

## <a name="remarks"></a>说明

此操作与使用 **"查找和替换"** 对话框中的 **"查找下一个"** 按钮的效果相同。


> [!NOTE]
> <P>[!注释] 对于表、查询和窗体，虽然 <STRONG>FindRecord</STRONG> 操作与 <STRONG>"开始"</STRONG>选项卡上的 <STRONG>"查找"</STRONG>命令相对应，但并不与"代码"窗口中 <STRONG>"编辑"</STRONG>菜单上的 <STRONG>"查找"</STRONG>命令相对应。不能使用 <STRONG>FindRecord</STRONG> 或 <STRONG>FindNextRecord</STRONG> 操作搜索模块中的文本。</P>




> [!TIP]
> <P>如果您已将<STRONG>FindRecord</STRONG>操作<STRONG>只搜索当前字段</STRONG>参数设置为<STRONG>是</STRONG>，您可能需要使用<STRONG>GoToControl</STRONG>操作将焦点移到控件包含使用<STRONG>之前要搜索的数据FindNextRecord</STRONG>操作。</P>



在执行 **FindNextRecord** 宏操作时，如果当前所选的文本与搜索文本相同，则会从所选文本之后开始在包含该文本的同一字段和同一记录中进行搜索；否则将从当前记录的起始位置开始搜索。这样可以找到单个记录中可能出现的符合相同搜索条件的多个实例。

但请注意，如果使用命令按钮运行包含 **FindNextRecord** 操作的宏，则将重复找到符合搜索条件的第一个实例。出现这种情况的原因是，单击命令按钮会将焦点从包含匹配值的字段中移走。这样， **FindNextRecord** 操作将从记录的起始位置开始搜索。为了避免此问题，请使用不会更改焦点的技术运行该宏，例如使用自定义工具栏按钮或在 AutoKeys 宏中定义的组合键。此外，也可以在执行 **FindNextRecord** 操作之前将宏中的焦点设置为包含搜索条件的字段。

如果您使用的命令按钮运行包含**FindRecord**操作，**查找第一个**参数设置为**否**的宏，也会发生相同的行为。

若要在 Visual Basic for Applications 模块中运行 **FindNextRecord** 操作，请使用 **DoCmd** 对象的 **FindNext** 方法。

