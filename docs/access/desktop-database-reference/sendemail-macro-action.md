---
title: SendEmail 宏操作
TOCTitle: SendEmail macro action
ms:assetid: 84ff6b46-d239-4716-9964-5b909656d347
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196780(v=office.15)
ms:contentKeyID: 48546046
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c0fa220b3088cde46b0e82631c06520afd839c64
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314649"
---
# <a name="sendemail-macro-action"></a><span data-ttu-id="15d6a-102">SendEmail 宏操作</span><span class="sxs-lookup"><span data-stu-id="15d6a-102">SendEmail macro action</span></span>

<span data-ttu-id="15d6a-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="15d6a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="15d6a-104">**SendEmail**操作会发送一封电子邮件。</span><span class="sxs-lookup"><span data-stu-id="15d6a-104">The **SendEmail** action sends an email message.</span></span>

> [!NOTE]
> <span data-ttu-id="15d6a-105">**SendEmail** 操作仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="15d6a-105">The **SendEmail** action is available only in Data Macros.</span></span>

## <a name="setting"></a><span data-ttu-id="15d6a-106">Setting</span><span class="sxs-lookup"><span data-stu-id="15d6a-106">Setting</span></span>

<span data-ttu-id="15d6a-107">**SendEmail** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="15d6a-107">The **SendEmail** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="15d6a-108">参数</span><span class="sxs-lookup"><span data-stu-id="15d6a-108">Argument</span></span></p></th>
<th><p><span data-ttu-id="15d6a-109">必需</span><span class="sxs-lookup"><span data-stu-id="15d6a-109">Required</span></span></p></th>
<th><p><span data-ttu-id="15d6a-110">说明</span><span class="sxs-lookup"><span data-stu-id="15d6a-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15d6a-111"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="15d6a-111"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="15d6a-112">是</span><span class="sxs-lookup"><span data-stu-id="15d6a-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="15d6a-113">要将其名称放在邮件的 "<strong>收件人</strong>" 行中的邮件的收件人。使用分号 (;) 将在此参数中指定的收件人姓名 (以及 " <em>Cc</em> " 和<em>"Bcc</em> " 参数) 隔开。</span><span class="sxs-lookup"><span data-stu-id="15d6a-113">The recipients of the message whose names you want to put on the <strong>To</strong> line in the message.Separate the recipient names that you specify in this argument (and in the <em>Cc</em> and <em>Bcc</em> arguments) with a semicolon (;).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d6a-114"><strong>Cc</strong></span><span class="sxs-lookup"><span data-stu-id="15d6a-114"><strong>Cc</strong></span></span></p></td>
<td><p><span data-ttu-id="15d6a-115">否</span><span class="sxs-lookup"><span data-stu-id="15d6a-115">No</span></span></p></td>
<td><p><span data-ttu-id="15d6a-116">要将其姓名置于邮件的 "抄送" (&quot;抄送&quot;) 行中的邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="15d6a-116">The message recipients whose names you want to put on the Cc (&quot;carbon copy&quot;) line in the message.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d6a-117"><strong>Bcc</strong></span><span class="sxs-lookup"><span data-stu-id="15d6a-117"><strong>Bcc</strong></span></span></p></td>
<td><p><span data-ttu-id="15d6a-118">否</span><span class="sxs-lookup"><span data-stu-id="15d6a-118">No</span></span></p></td>
<td><p><span data-ttu-id="15d6a-119">要将其姓名置于邮件的 "密件抄送" (&quot;密件抄送&quot;) 行中的邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="15d6a-119">The message recipients whose names you want to put on the Bcc (&quot;blind carbon copy&quot;) line in the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d6a-120"><strong>Subject</strong></span><span class="sxs-lookup"><span data-stu-id="15d6a-120"><strong>Subject</strong></span></span></p></td>
<td><p><span data-ttu-id="15d6a-121">否</span><span class="sxs-lookup"><span data-stu-id="15d6a-121">No</span></span></p></td>
<td><p><span data-ttu-id="15d6a-p101">邮件的主题。此文本显示在邮件的“主题”<strong></strong>行中。</span><span class="sxs-lookup"><span data-stu-id="15d6a-p101">The subject of the message. This text appears on the <strong>Subject</strong> line in the message.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d6a-124"><strong>Body</strong></span><span class="sxs-lookup"><span data-stu-id="15d6a-124"><strong>Body</strong></span></span></p></td>
<td><p><span data-ttu-id="15d6a-125">否</span><span class="sxs-lookup"><span data-stu-id="15d6a-125">No</span></span></p></td>
<td><p><span data-ttu-id="15d6a-p102">要在邮件的正文中包括的文本。如果将此参数留空，则邮件中不会包括其他文本。</span><span class="sxs-lookup"><span data-stu-id="15d6a-p102">The text that you want to include in the main body of the mail message. If you leave this argument blank, no additional text is included in the message.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="15d6a-128">注解</span><span class="sxs-lookup"><span data-stu-id="15d6a-128">Remarks</span></span>

<span data-ttu-id="15d6a-129">**SendEmail** 操作仅适用于 **[删除后](after-delete-macro-event.md)** 、 **[插入后](after-insert-macro-event.md)** 和 **[更新后](after-update-macro-event.md)** 宏事件。</span><span class="sxs-lookup"><span data-stu-id="15d6a-129">The **SendEmail** action is available only in the **[After Delete](after-delete-macro-event.md)**, **[After Insert](after-insert-macro-event.md)**, and **[After Update](after-update-macro-event.md)** macro events.</span></span>

<span data-ttu-id="15d6a-130">**SendEmail** 操作不显示用于编辑的邮件。</span><span class="sxs-lookup"><span data-stu-id="15d6a-130">The **SendEmail** action does not display the message for editing.</span></span>

