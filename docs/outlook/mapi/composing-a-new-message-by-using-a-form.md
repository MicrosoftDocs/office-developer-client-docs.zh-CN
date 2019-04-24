---
title: 使用表单撰写新邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c92181c4-79ca-4310-8bf1-2bc335c8e0cd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1c5ba8631ba39309b7131440f04564f80b5dbb57
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335124"
---
# <a name="composing-a-new-message-by-using-a-form"></a><span data-ttu-id="00216-103">使用表单撰写新邮件</span><span class="sxs-lookup"><span data-stu-id="00216-103">Composing a New Message by Using a Form</span></span>

  
  
<span data-ttu-id="00216-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="00216-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="00216-105">若要使用表单撰写新邮件, 请首先创建一个新的自定义邮件对象。</span><span class="sxs-lookup"><span data-stu-id="00216-105">To use a form to compose a new message, first create a new custom message object.</span></span>
  
 <span data-ttu-id="00216-106">**使用表单撰写新邮件**</span><span class="sxs-lookup"><span data-stu-id="00216-106">**To compose a new message using a form**</span></span>
  
1. <span data-ttu-id="00216-107">调用表单管理器的[IMAPIFormMgr:: ResolveMessageClass](imapiformmgr-resolvemessageclass.md)方法以检索指向表单信息对象的指针, 即实现[IMAPIFormInfo: IMAPIProp](imapiforminfoimapiprop.md)接口的对象。</span><span class="sxs-lookup"><span data-stu-id="00216-107">Call the form manager's [IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md) method to retrieve a pointer to a form information object — an object that implements the [IMAPIFormInfo : IMAPIProp](imapiforminfoimapiprop.md) interface.</span></span> 
    
2. <span data-ttu-id="00216-108">在对[IMAPIFormMgr:: CreateForm](imapiformmgr-createform.md)的调用中传递指向表单信息对象的指针。</span><span class="sxs-lookup"><span data-stu-id="00216-108">Pass the pointer to the form information object in a call to [IMAPIFormMgr::CreateForm](imapiformmgr-createform.md).</span></span> <span data-ttu-id="00216-109">**CreateForm**加载适当的表单服务器。</span><span class="sxs-lookup"><span data-stu-id="00216-109">**CreateForm** loads the appropriate form server.</span></span> <span data-ttu-id="00216-110">此外, 将接口标识符传递给**CreateForm** , 以指定用于访问新邮件的接口。</span><span class="sxs-lookup"><span data-stu-id="00216-110">In addition, pass an interface identifier to **CreateForm** to specify the interface to be used to access the new message.</span></span> <span data-ttu-id="00216-111">通常情况下, 通过将 IID_IPersistMessage 传递给**CreateForm**来请求[IPersistMessage: IUnknown](ipersistmessageiunknown.md) 。</span><span class="sxs-lookup"><span data-stu-id="00216-111">Typically, you request [IPersistMessage : IUnknown](ipersistmessageiunknown.md) by passing IID_IPersistMessage to **CreateForm**.</span></span>
    
3. <span data-ttu-id="00216-112">通过调用[IPersistMessage:: Save](ipersistmessage-save.md)方法保存新邮件。</span><span class="sxs-lookup"><span data-stu-id="00216-112">Save the new message by calling its [IPersistMessage::Save](ipersistmessage-save.md) method.</span></span> <span data-ttu-id="00216-113">窗体服务器在创建邮件时, 应设置邮件的必需属性的值。</span><span class="sxs-lookup"><span data-stu-id="00216-113">The form server should set values for the message's required properties when it creates the message.</span></span> 
    
4. <span data-ttu-id="00216-114">使用以下两个策略之一加载邮件: [IMAPIFormMgr:: LoadForm](imapiformmgr-loadform.md)或[IMAPISession::P repareform](imapisession-prepareform.md)后接[IMAPISession:: ShowForm](imapisession-showform.md)。</span><span class="sxs-lookup"><span data-stu-id="00216-114">Load the message by using one of two strategies: [IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md) or [IMAPISession::PrepareForm](imapisession-prepareform.md) followed by [IMAPISession::ShowForm](imapisession-showform.md).</span></span> <span data-ttu-id="00216-115">有关这些策略的详细信息, 请参阅将[邮件加载到表单](loading-a-message-into-a-form.md)中。</span><span class="sxs-lookup"><span data-stu-id="00216-115">For more information about these strategies, see [Loading a Message Into a Form](loading-a-message-into-a-form.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="00216-116">将新的自定义邮件加载到表单服务器中时, 会有机会提高性能, 因为在处理的过程中, 您已经有机会获取有关邮件 (如邮件类) 的某些信息。 **ResolveMessageClass**和**CreateForm**调用。</span><span class="sxs-lookup"><span data-stu-id="00216-116">There are opportunities for performance gains when loading a new custom message into a form server because you will already have had an opportunity to get some information about the message — such as its message class — during the processing required for the **ResolveMessageClass** and **CreateForm** calls.</span></span> <span data-ttu-id="00216-117">因此, 您将能够在调用**LoadForm**之前, 简化在将[邮件加载到表单](loading-a-message-into-a-form.md)中所述的步骤之前所需的处理过程。</span><span class="sxs-lookup"><span data-stu-id="00216-117">Because of this, you will be able to simplify the processing required before calling **LoadForm** over that described in the topic [Loading a Message Into a Form](loading-a-message-into-a-form.md).</span></span> 
  

