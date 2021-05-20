---
title: 显示表单图标
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 197e72ab-f9d6-4889-a677-0ce4c27b1aad
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c93912d19f0ad3c3231092c82f27cec9e3f15b3e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438629"
---
# <a name="displaying-form-icons"></a><span data-ttu-id="d9e82-103">显示表单图标</span><span class="sxs-lookup"><span data-stu-id="d9e82-103">Displaying Form Icons</span></span>

  
  
<span data-ttu-id="d9e82-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d9e82-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d9e82-105">在文件夹中显示邮件列表时，如果将具有自定义邮件类的邮件与标准 IPM 区分，则用户会很有帮助。注意消息。</span><span class="sxs-lookup"><span data-stu-id="d9e82-105">When displaying a list of messages in a folder, it is helpful to your users if you distinguish messages with custom message classes from the standard IPM.Note messages.</span></span> <span data-ttu-id="d9e82-106">自定义邮件类对应于表单服务器，而表单服务器提供表示自己的图标。</span><span class="sxs-lookup"><span data-stu-id="d9e82-106">Custom message classes correspond to form servers, and form servers provide icons to represent themselves.</span></span> <span data-ttu-id="d9e82-107">您可以在邮件列表中显示这些图标，以在用户打开邮件之前提醒用户注意每封邮件类别。</span><span class="sxs-lookup"><span data-stu-id="d9e82-107">You can display these icons in the list of messages to alert users to each message's message class before the user opens the messages.</span></span> <span data-ttu-id="d9e82-108">通常，表单的 PR_MINI_ICON ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性中的图标是应该显示在邮件列表中的图标。 </span><span class="sxs-lookup"><span data-stu-id="d9e82-108">Typically, the icon in the form's **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) property is the one that should be displayed in the list of messages.</span></span> <span data-ttu-id="d9e82-109">表单 **还具有一** PR_ICON ([PidTagIcon](pidtagicon-canonical-property.md)) 属性，可在表单最小化时显示在 属性表。</span><span class="sxs-lookup"><span data-stu-id="d9e82-109">Forms also have a **PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) property that can be displayed when the form is minimized in a property sheet.</span></span>
  
 <span data-ttu-id="d9e82-110">**在不激活邮件类的窗体服务器的情况下获取邮件类的图标**</span><span class="sxs-lookup"><span data-stu-id="d9e82-110">**To get an icon for a message class without activating the form server for that message class**</span></span>
  
1. <span data-ttu-id="d9e82-111">调用 [IMAPIFormMgr：：OpenFormContainer](imapiformmgr-openformcontainer.md) 方法，获取 [指向 IMAPIFormContainer ： IUnknown](imapiformcontaineriunknown.md) 接口的指针。</span><span class="sxs-lookup"><span data-stu-id="d9e82-111">Call the [IMAPIFormMgr::OpenFormContainer](imapiformmgr-openformcontainer.md) method to get a pointer to an [IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md) interface.</span></span> 
    
2. <span data-ttu-id="d9e82-112">调用 [IMAPIFormContainer：：ResolveMessageClass](imapiformcontainer-resolvemessageclass.md) 方法，获取 [指向 IMAPIFormInfo ：IMAPIProp 接口的](imapiforminfoimapiprop.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="d9e82-112">Call the [IMAPIFormContainer::ResolveMessageClass](imapiformcontainer-resolvemessageclass.md) method to get a pointer to an [IMAPIFormInfo : IMAPIProp](imapiforminfoimapiprop.md) interface.</span></span> 
    
3. <span data-ttu-id="d9e82-113">调用 [IMAPIFormInfo：：MakeIconFromBinary](imapiforminfo-makeiconfrombinary.md) 方法获取图标句柄。</span><span class="sxs-lookup"><span data-stu-id="d9e82-113">Call the [IMAPIFormInfo::MakeIconFromBinary](imapiforminfo-makeiconfrombinary.md) method to get an icon handle.</span></span> 
    
<span data-ttu-id="d9e82-114">然后，可以使用标准 Win32 API 显示该图标。</span><span class="sxs-lookup"><span data-stu-id="d9e82-114">The icon can then be displayed using standard Win32 APIs.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d9e82-115">获得邮件类的图标后，请尽一切努力缓存该图标。</span><span class="sxs-lookup"><span data-stu-id="d9e82-115">Once you have the icon for a message class, make every effort to cache that icon.</span></span> <span data-ttu-id="d9e82-116">不缓存图标会严重影响客户端应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="d9e82-116">Not caching icons severely affects the performance of client applications.</span></span> <span data-ttu-id="d9e82-117">缓存图标时，请注意邮件类及其子类之间的关系。</span><span class="sxs-lookup"><span data-stu-id="d9e82-117">When caching icons, be careful of the relationships between message classes and their subclasses.</span></span> <span data-ttu-id="d9e82-118">例如，如果 IPM。注意.Meeting.Cancel 邮件类恰好解析回 IPM。请注意，不要假定 IPM 的所有子类。注意，应该使用 IPM 的图标。注意。</span><span class="sxs-lookup"><span data-stu-id="d9e82-118">For example, if the IPM.Note.Meeting.Cancel message class happens to resolve back to IPM.Note, do not assume that all subclasses of IPM.Note should use the icon for IPM.Note.</span></span> 
  

