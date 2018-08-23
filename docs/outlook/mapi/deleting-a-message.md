---
title: 删除邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9ed166b4-6b7b-478f-bbe5-4115bb818ac0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ad891a9884e72aa352dc114232cd5951c590272f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585099"
---
# <a name="deleting-a-message"></a><span data-ttu-id="8b8b1-103">删除邮件</span><span class="sxs-lookup"><span data-stu-id="8b8b1-103">Deleting a Message</span></span>

  
  
<span data-ttu-id="8b8b1-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8b8b1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8b8b1-105">当处于打开状态，并且用户阅读，或者关闭和用户正在查看的内容表时客户端可以删除一条消息。</span><span class="sxs-lookup"><span data-stu-id="8b8b1-105">A client can delete a message when it is open and the user is reading it, or when it is closed and the user is viewing the contents table.</span></span> <span data-ttu-id="8b8b1-106">若要防止用户无意删除一条消息，MAPI 时，可定义邮件删除为两个步骤：</span><span class="sxs-lookup"><span data-stu-id="8b8b1-106">To protect a user from inadvertently removing a message, MAPI defines message deletion as a two step process:</span></span>
  
1. <span data-ttu-id="8b8b1-107">移到被指定为已删除邮件文件夹的文件夹将其标记为删除一条消息 — **PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)) 属性中存储其项标识符的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8b8b1-107">Mark a message for deletion by moving it to the folder that has been designated as the Deleted Items folder — the folder whose entry identifier is stored in the **PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)) property.</span></span> 
    
2. <span data-ttu-id="8b8b1-108">通过调用[IMAPIFolder::DeleteMessages](imapifolder-deletemessages.md)方法删除邮件。</span><span class="sxs-lookup"><span data-stu-id="8b8b1-108">Remove the message by calling the [IMAPIFolder::DeleteMessages](imapifolder-deletemessages.md) method.</span></span> 
    
<span data-ttu-id="8b8b1-109">当用户选择要删除一条消息已删除邮件文件夹之外的文件夹中时，将其标记为删除。</span><span class="sxs-lookup"><span data-stu-id="8b8b1-109">When a user chooses to delete a message in a folder other than the Deleted Items folder, mark it for deletion.</span></span> <span data-ttu-id="8b8b1-110">仅当用户选择从已删除邮件文件夹中的邮件时，才应邮件物理删除从工作站。</span><span class="sxs-lookup"><span data-stu-id="8b8b1-110">Only when a user selects messages from within the Deleted Items folder should the messages be physically removed from the workstation.</span></span> <span data-ttu-id="8b8b1-111">您可以提示用户确认用户真正用于执行删除操作。</span><span class="sxs-lookup"><span data-stu-id="8b8b1-111">You can prompt the user to verify that the user really intended to perform the deletion.</span></span>
  
 <span data-ttu-id="8b8b1-112">**若要删除一条消息**</span><span class="sxs-lookup"><span data-stu-id="8b8b1-112">**To delete a message**</span></span>
  
1. <span data-ttu-id="8b8b1-113">与用户确认即将删除是有意。</span><span class="sxs-lookup"><span data-stu-id="8b8b1-113">Confirm with the user that the impending deletion is intentional.</span></span>
    
2. <span data-ttu-id="8b8b1-114">确定要删除的文件夹的父级。</span><span class="sxs-lookup"><span data-stu-id="8b8b1-114">Determine the parent of the folder to be deleted.</span></span> <span data-ttu-id="8b8b1-115">如果是已删除邮件文件夹还是已删除邮件文件夹中的子文件夹，调用[IMAPIFolder::DeleteMessages](imapifolder-deletemessages.md)要删除该消息。</span><span class="sxs-lookup"><span data-stu-id="8b8b1-115">If it is the Deleted Items folder or a subfolder within the Deleted Items folder, call [IMAPIFolder::DeleteMessages](imapifolder-deletemessages.md) to remove the message.</span></span> 
    
3. <span data-ttu-id="8b8b1-116">如果文件夹不包含在已删除邮件文件夹中，调用[IMAPIFolder::CopyMessages](imapifolder-copymessages.md)设置重定位到已删除邮件文件夹的邮件 MESSAGE_MOVE 标志。</span><span class="sxs-lookup"><span data-stu-id="8b8b1-116">If the folder is not contained within the Deleted Items folder, call [IMAPIFolder::CopyMessages](imapifolder-copymessages.md) with the MESSAGE_MOVE flag set to relocate the message to the Deleted Items folder.</span></span> 
    

