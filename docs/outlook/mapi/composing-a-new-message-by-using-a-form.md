---
title: 使用表单撰写新邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c92181c4-79ca-4310-8bf1-2bc335c8e0cd
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 667d7afe1772786507ffc8eb75f901439ada61d3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587865"
---
# <a name="composing-a-new-message-by-using-a-form"></a><span data-ttu-id="1c4b9-103">使用表单撰写新邮件</span><span class="sxs-lookup"><span data-stu-id="1c4b9-103">Composing a New Message by Using a Form</span></span>

  
  
<span data-ttu-id="1c4b9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1c4b9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1c4b9-105">若要使用窗体撰写新邮件，请首先创建一个新的自定义消息对象。</span><span class="sxs-lookup"><span data-stu-id="1c4b9-105">To use a form to compose a new message, first create a new custom message object.</span></span>
  
 <span data-ttu-id="1c4b9-106">**撰写新邮件使用窗体**</span><span class="sxs-lookup"><span data-stu-id="1c4b9-106">**To compose a new message using a form**</span></span>
  
1. <span data-ttu-id="1c4b9-107">调用该窗体管理器的[IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md)方法来检索指向窗体信息对象 — 一个对象，实现[IMAPIFormInfo: IMAPIProp](imapiforminfoimapiprop.md)接口。</span><span class="sxs-lookup"><span data-stu-id="1c4b9-107">Call the form manager's [IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md) method to retrieve a pointer to a form information object — an object that implements the [IMAPIFormInfo : IMAPIProp](imapiforminfoimapiprop.md) interface.</span></span> 
    
2. <span data-ttu-id="1c4b9-108">将指针传递给[IMAPIFormMgr::CreateForm](imapiformmgr-createform.md)调用中的窗体信息对象。</span><span class="sxs-lookup"><span data-stu-id="1c4b9-108">Pass the pointer to the form information object in a call to [IMAPIFormMgr::CreateForm](imapiformmgr-createform.md).</span></span> <span data-ttu-id="1c4b9-109">**CreateForm**加载的相应窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="1c4b9-109">**CreateForm** loads the appropriate form server.</span></span> <span data-ttu-id="1c4b9-110">此外，将接口标识传递给**CreateForm**来指定要用于访问新邮件的接口。</span><span class="sxs-lookup"><span data-stu-id="1c4b9-110">In addition, pass an interface identifier to **CreateForm** to specify the interface to be used to access the new message.</span></span> <span data-ttu-id="1c4b9-111">通常情况下，您请求[IPersistMessage: IUnknown](ipersistmessageiunknown.md)通过将 IID_IPersistMessage 传递给**CreateForm**。</span><span class="sxs-lookup"><span data-stu-id="1c4b9-111">Typically, you request [IPersistMessage : IUnknown](ipersistmessageiunknown.md) by passing IID_IPersistMessage to **CreateForm**.</span></span>
    
3. <span data-ttu-id="1c4b9-112">通过调用其[IPersistMessage::Save](ipersistmessage-save.md)方法保存新邮件。</span><span class="sxs-lookup"><span data-stu-id="1c4b9-112">Save the new message by calling its [IPersistMessage::Save](ipersistmessage-save.md) method.</span></span> <span data-ttu-id="1c4b9-113">在创建邮件时，窗体服务器应设置消息的必需属性的值。</span><span class="sxs-lookup"><span data-stu-id="1c4b9-113">The form server should set values for the message's required properties when it creates the message.</span></span> 
    
4. <span data-ttu-id="1c4b9-114">使用两种策略之一加载消息： [IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md)或[IMAPISession::PrepareForm](imapisession-prepareform.md)后跟[IMAPISession::ShowForm](imapisession-showform.md)。</span><span class="sxs-lookup"><span data-stu-id="1c4b9-114">Load the message by using one of two strategies: [IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md) or [IMAPISession::PrepareForm](imapisession-prepareform.md) followed by [IMAPISession::ShowForm](imapisession-showform.md).</span></span> <span data-ttu-id="1c4b9-115">有关这些策略的详细信息，请参阅[加载邮件到窗体](loading-a-message-into-a-form.md)。</span><span class="sxs-lookup"><span data-stu-id="1c4b9-115">For more information about these strategies, see [Loading a Message Into a Form](loading-a-message-into-a-form.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="1c4b9-116">有机会性能提升时将新的自定义消息加载到窗体服务器，因为您已经有机会获取一些有关邮件信息将 — 例如其邮件类别 —**所需的处理期间ResolveMessageClass**和**CreateForm**呼叫。</span><span class="sxs-lookup"><span data-stu-id="1c4b9-116">There are opportunities for performance gains when loading a new custom message into a form server because you will already have had an opportunity to get some information about the message — such as its message class — during the processing required for the **ResolveMessageClass** and **CreateForm** calls.</span></span> <span data-ttu-id="1c4b9-117">因此，您将能够简化过去[加载邮件到窗体](loading-a-message-into-a-form.md)的主题中所述调用**LoadForm**之前所需的处理。</span><span class="sxs-lookup"><span data-stu-id="1c4b9-117">Because of this, you will be able to simplify the processing required before calling **LoadForm** over that described in the topic [Loading a Message Into a Form](loading-a-message-into-a-form.md).</span></span> 
  

