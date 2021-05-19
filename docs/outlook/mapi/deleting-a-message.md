---
title: 删除邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9ed166b4-6b7b-478f-bbe5-4115bb818ac0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 663eebfcd1b8862b22d8c822957024c4f31499de
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433162"
---
# <a name="deleting-a-message"></a><span data-ttu-id="4831d-103">删除邮件</span><span class="sxs-lookup"><span data-stu-id="4831d-103">Deleting a Message</span></span>

  
  
<span data-ttu-id="4831d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4831d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4831d-105">客户端可以在邮件打开时、用户阅读邮件时、关闭消息和用户查看内容表时删除该消息。</span><span class="sxs-lookup"><span data-stu-id="4831d-105">A client can delete a message when it is open and the user is reading it, or when it is closed and the user is viewing the contents table.</span></span> <span data-ttu-id="4831d-106">若要防止用户意外删除邮件，MAPI 将邮件删除定义为两个步骤：</span><span class="sxs-lookup"><span data-stu-id="4831d-106">To protect a user from inadvertently removing a message, MAPI defines message deletion as a two step process:</span></span>
  
1. <span data-ttu-id="4831d-107">将邮件移动到已指定为"已删除邮件"文件夹的文件夹（其条目标识符存储在 PR_IPM_WASTEBASKET_ENTRYID ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md) **)** 属性中）来标记邮件进行删除。</span><span class="sxs-lookup"><span data-stu-id="4831d-107">Mark a message for deletion by moving it to the folder that has been designated as the Deleted Items folder — the folder whose entry identifier is stored in the **PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)) property.</span></span> 
    
2. <span data-ttu-id="4831d-108">通过调用 [IMAPIFolder：:D EleteMessages](imapifolder-deletemessages.md) 方法删除消息。</span><span class="sxs-lookup"><span data-stu-id="4831d-108">Remove the message by calling the [IMAPIFolder::DeleteMessages](imapifolder-deletemessages.md) method.</span></span> 
    
<span data-ttu-id="4831d-109">当用户选择删除文件夹中除"已删除邮件"文件夹外的邮件时，请将其标记为删除。</span><span class="sxs-lookup"><span data-stu-id="4831d-109">When a user chooses to delete a message in a folder other than the Deleted Items folder, mark it for deletion.</span></span> <span data-ttu-id="4831d-110">只有在用户从"已删除邮件"文件夹中选择邮件时，才应从工作站中实际删除这些邮件。</span><span class="sxs-lookup"><span data-stu-id="4831d-110">Only when a user selects messages from within the Deleted Items folder should the messages be physically removed from the workstation.</span></span> <span data-ttu-id="4831d-111">您可以提示用户验证用户是否确实要执行删除操作。</span><span class="sxs-lookup"><span data-stu-id="4831d-111">You can prompt the user to verify that the user really intended to perform the deletion.</span></span>
  
 <span data-ttu-id="4831d-112">**删除邮件**</span><span class="sxs-lookup"><span data-stu-id="4831d-112">**To delete a message**</span></span>
  
1. <span data-ttu-id="4831d-113">与用户确认即将删除是有意的。</span><span class="sxs-lookup"><span data-stu-id="4831d-113">Confirm with the user that the impending deletion is intentional.</span></span>
    
2. <span data-ttu-id="4831d-114">确定要删除的文件夹的父文件夹。</span><span class="sxs-lookup"><span data-stu-id="4831d-114">Determine the parent of the folder to be deleted.</span></span> <span data-ttu-id="4831d-115">如果是"已删除邮件"文件夹或"已删除邮件"文件夹中的子文件夹，请调用 [IMAPIFolder：:D eleteMessages](imapifolder-deletemessages.md) 删除邮件。</span><span class="sxs-lookup"><span data-stu-id="4831d-115">If it is the Deleted Items folder or a subfolder within the Deleted Items folder, call [IMAPIFolder::DeleteMessages](imapifolder-deletemessages.md) to remove the message.</span></span> 
    
3. <span data-ttu-id="4831d-116">如果该文件夹未包含在"已删除邮件"文件夹中，请调用 [IMAPIFolder：：CopyMessages，](imapifolder-copymessages.md) 同时将 MESSAGE_MOVE 标志设置为将邮件重定位到"已删除邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="4831d-116">If the folder is not contained within the Deleted Items folder, call [IMAPIFolder::CopyMessages](imapifolder-copymessages.md) with the MESSAGE_MOVE flag set to relocate the message to the Deleted Items folder.</span></span> 
    

