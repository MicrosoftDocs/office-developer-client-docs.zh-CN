---
title: Find 方法-ActiveX 数据对象 (ADO)
TOCTitle: Find method (ADO)
ms:assetid: a7cc9ceb-fdb9-73e2-8328-70b174f93cda
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249776(v=office.15)
ms:contentKeyID: 48546887
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b37f5930f9a9a36603700a1d27458527f128ad34
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922032"
---
# <a name="find-method-ado"></a><span data-ttu-id="a56ce-102">Find 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="a56ce-102">Find method (ADO)</span></span>


<span data-ttu-id="a56ce-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="a56ce-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="a56ce-p101">用于在 [Recordset](recordset-object-ado.md) 中搜索满足指定条件的行。可以选择性地指定搜索方向、起始行和与起始行的偏移量。如果满足条件，当前行位置将设置为找到的记录位置；否则，该位置设置为 **Recordset** 的末尾（或开头）。</span><span class="sxs-lookup"><span data-stu-id="a56ce-p101">Searches a [Recordset](recordset-object-ado.md) for the row that satisfies the specified criteria. Optionally, the direction of the search, starting row, and offset from the starting row may be specified. If the criteria is met, the current row position is set on the found record; otherwise, the position is set to the end (or start) of the **Recordset**.</span></span>

## <a name="syntax"></a><span data-ttu-id="a56ce-107">语法</span><span class="sxs-lookup"><span data-stu-id="a56ce-107">Syntax</span></span>

<span data-ttu-id="a56ce-108">查找 （*条件*， *SkipRows*、 *SearchDirection*，*启动*）</span><span class="sxs-lookup"><span data-stu-id="a56ce-108">Find (*Criteria*, *SkipRows*, *SearchDirection*, *Start*)</span></span>

## <a name="parameters"></a><span data-ttu-id="a56ce-109">参数</span><span class="sxs-lookup"><span data-stu-id="a56ce-109">Parameters</span></span>

  - <span data-ttu-id="a56ce-110">*Criteria*</span><span class="sxs-lookup"><span data-stu-id="a56ce-110">*Criteria*</span></span>

  - <span data-ttu-id="a56ce-111">**字符串型** 值，包含用于指定在搜索中使用的列名、比较运算符和值的语句。</span><span class="sxs-lookup"><span data-stu-id="a56ce-111">A **String** value that contains a statement specifying the column name, comparison operator, and value to use in the search.</span></span>

  - <span data-ttu-id="a56ce-112">*SkipRows*</span><span class="sxs-lookup"><span data-stu-id="a56ce-112">*SkipRows*</span></span>

  - <span data-ttu-id="a56ce-p102">可选**。**长整型\**值，默认值为零，用于指定与当前行的行偏移量或*开始\*书签，以开始搜索。默认情况下，搜索将从当前行开始。</span><span class="sxs-lookup"><span data-stu-id="a56ce-p102">Optional *.* A **Long** value, whose default value is zero, that specifies the row offset from the current row or *Start* bookmark to begin the search. By default, the search will start on the current row.</span></span>

  - <span data-ttu-id="a56ce-116">*SearchDirection*</span><span class="sxs-lookup"><span data-stu-id="a56ce-116">*SearchDirection*</span></span>

  - <span data-ttu-id="a56ce-p103">可选 *。*[SearchDirectionEnum](searchdirectionenum.md) 值，指定搜索应从当前行开始还是从搜索方向上的下一个可用行开始。如果该值为 **adSearchForward**，则不成功的搜索在 **Recordset** 的末尾停止。如果该值为 **adSearchBackward**，则不成功的搜索在 **Recordset** 的开头停止。</span><span class="sxs-lookup"><span data-stu-id="a56ce-p103">Optional *.* A [SearchDirectionEnum](searchdirectionenum.md) value that specifies whether the search should begin on the current row or the next available row in the direction of the search. An unsuccessful search stops at the end of the **Recordset** if the value is **adSearchForward**. An unsuccessful search stops at the start of the **Recordset** if the value is **adSearchBackward**.</span></span>

  - <span data-ttu-id="a56ce-121">*Start*</span><span class="sxs-lookup"><span data-stu-id="a56ce-121">*Start*</span></span>

  - <span data-ttu-id="a56ce-p104">可选。 **变量型** 书签，充当搜索的开始位置。</span><span class="sxs-lookup"><span data-stu-id="a56ce-p104">Optional. A **Variant** bookmark that functions as the starting position for the search.</span></span>

## <a name="remarks"></a><span data-ttu-id="a56ce-124">备注</span><span class="sxs-lookup"><span data-stu-id="a56ce-124">Remarks</span></span>

<span data-ttu-id="a56ce-p105">*Criteria* 中只能指定一个列名称。该方法不支持多列搜索。</span><span class="sxs-lookup"><span data-stu-id="a56ce-p105">Only a single-column name may be specified in *criteria*. This method does not support multi-column searches.</span></span>

<span data-ttu-id="a56ce-127">*条件*中的比较运算符可能"**\>**"（大于），"**\<**"（小于），"="（等于），"\>="（大于或等于），"\<="（小于或等于），"\<\>"（不等于），或"like"（模式匹配）。</span><span class="sxs-lookup"><span data-stu-id="a56ce-127">The comparison operator in *Criteria* may be "**\>**" (greater than), "**\<**" (less than), "=" (equal), "\>=" (greater than or equal), "\<=" (less than or equal), "\<\>" (not equal), or "like" (pattern matching).</span></span>

<span data-ttu-id="a56ce-128">*条件*中的值可以是字符串、 浮点数或日期。</span><span class="sxs-lookup"><span data-stu-id="a56ce-128">The value in *Criteria* may be a string, floating-point number, or date.</span></span> <span data-ttu-id="a56ce-129">用单引号分隔字符串值或"\#"（数字标记） 标记 (例如，"状态 WA ="或"状态 = \#WA\#")。</span><span class="sxs-lookup"><span data-stu-id="a56ce-129">String values are delimited with single quotes or "\#" (number sign) marks (for example, "state = 'WA'" or "state = \#WA\#").</span></span> <span data-ttu-id="a56ce-130">日期值分隔与"\#"（数字标记） 标记 (例如，"启动\_日期\> \#97-7-22\#") 和可以包含小时、 分钟和秒以指示时间戳，但不是应包含毫秒或将发生错误.</span><span class="sxs-lookup"><span data-stu-id="a56ce-130">Date values are delimited with "\#" (number sign) marks (for example, "start\_date \> \#7/22/97\#") and can contain hours, minutes and seconds to indicate time stamps but should not contain milliseconds or errors will occur.</span></span>

<span data-ttu-id="a56ce-p107">如果比较运算符是"like"，则字符串值中可以包含星号 (\*)，以查找一次或多次出现的任何字符或子字符串。例如，"state like 'M\*'"与 Maine 和 Massachusetts 相匹配。还可以使用前导和尾随星号来查找包含在值中的子字符串。例如，"state like '\*as\*'"与 Alaska、Arkansas 和 Massachusetts 相匹配。</span><span class="sxs-lookup"><span data-stu-id="a56ce-p107">If the comparison operator is "like", the string value may contain an asterisk (\*) to find one or more occurrences of any character or substring. For example, "state like 'M\*'" matches Maine and Massachusetts. You can also use leading and trailing asterisks to find a substring contained within the values. For example, "state like '\*as\*'" matches Alaska, Arkansas, and Massachusetts.</span></span>

<span data-ttu-id="a56ce-p108">星号只能在条件字符串的末尾使用，或者同时在条件字符串的开头和末尾使用，如上所述。不能将星号用作前导通配符 ("\*str") 或嵌入式通配符 ("s\*r")。否则将导致错误。</span><span class="sxs-lookup"><span data-stu-id="a56ce-p108">Asterisks can be used only at the end of a criteria string, or together at both the beginning and end of a criteria string, as shown above. You cannot use the asterisk as a leading wildcard ('\*str'), or embedded wildcard ('s\*r'). This will cause an error.</span></span>


> [!NOTE]
> <P><span data-ttu-id="a56ce-p109">[!注释] 如果当前行位置不是在调用 <STRONG>Find</STRONG> 之前设置的，将发生错误。设置行位置的任何方法（如 <A href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</A>）都应该在调用 <STRONG>Find</STRONG> 之前调用。</span><span class="sxs-lookup"><span data-stu-id="a56ce-p109">An error will occur if a current row position is not set before calling <STRONG>Find</STRONG>. Any method that sets row position, such as <A href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</A>, should be called before calling <STRONG>Find</STRONG>.</span></span></P>




> [!NOTE]
> <P><span data-ttu-id="a56ce-p110">[!注释] 如果对记录集调用 <STRONG>Find</STRONG> 方法，且记录集中的当前位置位于最后一个记录或文件末尾 (EOF)，您将找不到任何内容。您需要调用 <STRONG>MoveFirst</STRONG> 方法将当前位置/游标设置在记录集的开头。</span><span class="sxs-lookup"><span data-stu-id="a56ce-p110">If you call the <STRONG>Find</STRONG> method on a recordset, and the current position in the recordset is at the last record or end of file (EOF), you will not find anything. You need to call the <STRONG>MoveFirst</STRONG> method to set the current position/cursor to the beginning of the recordset.</span></span></P>


