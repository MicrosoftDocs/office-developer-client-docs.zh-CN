---
title: SendEmail 宏操作
TOCTitle: SendEmail Macro Action
ms:assetid: 84ff6b46-d239-4716-9964-5b909656d347
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196780(v=office.15)
ms:contentKeyID: 48546046
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: db82c2d0c8350d517044df5848f8c264b92e928d
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466587"
---
# <a name="sendemail-macro-action"></a><span data-ttu-id="214be-102">SendEmail 宏操作</span><span class="sxs-lookup"><span data-stu-id="214be-102">SendEmail Macro Action</span></span>


<span data-ttu-id="214be-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="214be-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="214be-104">**SendEmail** 操作可发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="214be-104">The **SendEmail** action sends an e-mail message.</span></span>


> [!NOTE]
> <P><span data-ttu-id="214be-105">[!注释] <STRONG>SendEmail</STRONG> 操作仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="214be-105">The <STRONG>SendEmail</STRONG> action is available only in Data Macros.</span></span></P>



## <a name="setting"></a><span data-ttu-id="214be-106">设置</span><span class="sxs-lookup"><span data-stu-id="214be-106">Setting</span></span>

<span data-ttu-id="214be-107">**SendEmail** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="214be-107">The **SendEmail** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="214be-108">参数</span><span class="sxs-lookup"><span data-stu-id="214be-108">Argument</span></span></p></th>
<th><p><span data-ttu-id="214be-109">是否必需</span><span class="sxs-lookup"><span data-stu-id="214be-109">Required</span></span></p></th>
<th><p><span data-ttu-id="214be-110">说明</span><span class="sxs-lookup"><span data-stu-id="214be-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="214be-111"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="214be-111"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="214be-112">是</span><span class="sxs-lookup"><span data-stu-id="214be-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="214be-113">您想要放在邮件中的<strong>到</strong>行上将其姓名的收件人。分隔用分号 （;） 指定此参数中 （以及<em>Cc</em>和<em>Bcc</em>参数） 的收件人姓名。</span><span class="sxs-lookup"><span data-stu-id="214be-113">The recipients of the message whose names you want to put on the <strong>To</strong> line in the message.Separate the recipient names that you specify in this argument (and in the <em>Cc</em> and <em>Bcc</em> arguments) with a semicolon (;).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="214be-114"><strong>Cc</strong></span><span class="sxs-lookup"><span data-stu-id="214be-114"><strong>Cc</strong></span></span></p></td>
<td><p><span data-ttu-id="214be-115">否</span><span class="sxs-lookup"><span data-stu-id="214be-115">No</span></span></p></td>
<td><p><span data-ttu-id="214be-116">邮件的收件人，您想要置于抄送将其姓名 (&quot;抄送&quot;) 邮件行中的。</span><span class="sxs-lookup"><span data-stu-id="214be-116">The message recipients whose names you want to put on the Cc (&quot;carbon copy&quot;) line in the message.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="214be-117"><strong>Bcc</strong></span><span class="sxs-lookup"><span data-stu-id="214be-117"><strong>Bcc</strong></span></span></p></td>
<td><p><span data-ttu-id="214be-118">否</span><span class="sxs-lookup"><span data-stu-id="214be-118">No</span></span></p></td>
<td><p><span data-ttu-id="214be-119">邮件的收件人，您想要置于密件抄送将其姓名 (&quot;密件抄送副本&quot;) 邮件行中的。</span><span class="sxs-lookup"><span data-stu-id="214be-119">The message recipients whose names you want to put on the Bcc (&quot;blind carbon copy&quot;) line in the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="214be-120"><strong>Subject</strong></span><span class="sxs-lookup"><span data-stu-id="214be-120"><strong>Subject</strong></span></span></p></td>
<td><p><span data-ttu-id="214be-121">否</span><span class="sxs-lookup"><span data-stu-id="214be-121">No</span></span></p></td>
<td><p><span data-ttu-id="214be-122">邮件的主题。</span><span class="sxs-lookup"><span data-stu-id="214be-122">The subject of the message.</span></span> <span data-ttu-id="214be-123">此文本出现在邮件中的<strong>主题</strong>行上。</span><span class="sxs-lookup"><span data-stu-id="214be-123">This text appears on the <strong>Subject</strong> line in the message.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="214be-124"><strong>Body</strong></span><span class="sxs-lookup"><span data-stu-id="214be-124"><strong>Body</strong></span></span></p></td>
<td><p><span data-ttu-id="214be-125">否</span><span class="sxs-lookup"><span data-stu-id="214be-125">No</span></span></p></td>
<td><p><span data-ttu-id="214be-p102">要在邮件的正文中包括的文本。如果将此参数留空，则邮件中不会包括其他文本。</span><span class="sxs-lookup"><span data-stu-id="214be-p102">The text that you want to include in the main body of the mail message. If you leave this argument blank, no additional text is included in the message.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="214be-128">注释</span><span class="sxs-lookup"><span data-stu-id="214be-128">Remarks</span></span>

<span data-ttu-id="214be-129">**SendEmail** 操作仅适用于 **[删除后](after-delete-macro-event.md)** 、 **[插入后](after-insert-macro-event.md)** 和 **[更新后](after-update-macro-event.md)** 宏事件。</span><span class="sxs-lookup"><span data-stu-id="214be-129">The **SendEmail** action is available only in the **[After Delete](after-delete-macro-event.md)**, **[After Insert](after-insert-macro-event.md)**, and **[After Update](after-update-macro-event.md)** macro events.</span></span>

<span data-ttu-id="214be-130">**SendEmail** 操作不显示用于编辑的邮件。</span><span class="sxs-lookup"><span data-stu-id="214be-130">The **SendEmail** action does not display the message for editing.</span></span>

