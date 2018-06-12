---
title: 显示窗体图标
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 197e72ab-f9d6-4889-a677-0ce4c27b1aad
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b2e79e5568de38bee9a97c9df2598b30f1ba1bdf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774809"
---
# <a name="displaying-form-icons"></a><span data-ttu-id="8eae7-103">显示窗体图标</span><span class="sxs-lookup"><span data-stu-id="8eae7-103">Displaying Form Icons</span></span>

  
  
<span data-ttu-id="8eae7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8eae7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8eae7-105">在文件夹中显示的邮件的列表时, 很有用向用户如果从标准 IPM 区分自定义邮件类别的邮件。请注意消息。</span><span class="sxs-lookup"><span data-stu-id="8eae7-105">When displaying a list of messages in a folder, it is helpful to your users if you distinguish messages with custom message classes from the standard IPM.Note messages.</span></span> <span data-ttu-id="8eae7-106">自定义邮件类对应于窗体服务器和窗体服务器提供了图标表示本身。</span><span class="sxs-lookup"><span data-stu-id="8eae7-106">Custom message classes correspond to form servers, and form servers provide icons to represent themselves.</span></span> <span data-ttu-id="8eae7-107">用户打开邮件之前，您可以对每封邮件的邮件类的通知用户的邮件的列表中显示这些图标。</span><span class="sxs-lookup"><span data-stu-id="8eae7-107">You can display these icons in the list of messages to alert users to each message's message class before the user opens the messages.</span></span> <span data-ttu-id="8eae7-108">通常情况下，窗体的**PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性中的图标是应显示在列表中的邮件。</span><span class="sxs-lookup"><span data-stu-id="8eae7-108">Typically, the icon in the form's **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) property is the one that should be displayed in the list of messages.</span></span> <span data-ttu-id="8eae7-109">窗体也有属性表中的窗体最小化时可显示**PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="8eae7-109">Forms also have a **PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) property that can be displayed when the form is minimized in a property sheet.</span></span>
  
 <span data-ttu-id="8eae7-110">**要获取为邮件类的图标，而不激活的邮件类的窗体服务器**</span><span class="sxs-lookup"><span data-stu-id="8eae7-110">**To get an icon for a message class without activating the form server for that message class**</span></span>
  
1. <span data-ttu-id="8eae7-111">调用[IMAPIFormMgr::OpenFormContainer](imapiformmgr-openformcontainer.md)方法以获取一个指向[IMAPIFormContainer: IUnknown](imapiformcontaineriunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="8eae7-111">Call the [IMAPIFormMgr::OpenFormContainer](imapiformmgr-openformcontainer.md) method to get a pointer to an [IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md) interface.</span></span> 
    
2. <span data-ttu-id="8eae7-112">调用[IMAPIFormContainer::ResolveMessageClass](imapiformcontainer-resolvemessageclass.md)方法以获取一个指向[IMAPIFormInfo: IMAPIProp](imapiforminfoimapiprop.md)接口。</span><span class="sxs-lookup"><span data-stu-id="8eae7-112">Call the [IMAPIFormContainer::ResolveMessageClass](imapiformcontainer-resolvemessageclass.md) method to get a pointer to an [IMAPIFormInfo : IMAPIProp](imapiforminfoimapiprop.md) interface.</span></span> 
    
3. <span data-ttu-id="8eae7-113">调用[IMAPIFormInfo::MakeIconFromBinary](imapiforminfo-makeiconfrombinary.md)方法以获取图标句柄。</span><span class="sxs-lookup"><span data-stu-id="8eae7-113">Call the [IMAPIFormInfo::MakeIconFromBinary](imapiforminfo-makeiconfrombinary.md) method to get an icon handle.</span></span> 
    
<span data-ttu-id="8eae7-114">然后可以使用标准 Win32 Api 显示的图标。</span><span class="sxs-lookup"><span data-stu-id="8eae7-114">The icon can then be displayed using standard Win32 APIs.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8eae7-115">邮件类的图标后，请尽力缓存的图标。</span><span class="sxs-lookup"><span data-stu-id="8eae7-115">Once you have the icon for a message class, make every effort to cache that icon.</span></span> <span data-ttu-id="8eae7-116">未缓存图标会严重影响客户端应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="8eae7-116">Not caching icons severely affects the performance of client applications.</span></span> <span data-ttu-id="8eae7-117">缓存图标时, 应谨慎的邮件类别以及其子类之间的关系。</span><span class="sxs-lookup"><span data-stu-id="8eae7-117">When caching icons, be careful of the relationships between message classes and their subclasses.</span></span> <span data-ttu-id="8eae7-118">例如，如果 IPM。Note.Meeting.Cancel 邮件类 IPM 回解决如此。请注意，不假定的所有 IPM 的子类。注意应该使用 IPM 图标。请注意。</span><span class="sxs-lookup"><span data-stu-id="8eae7-118">For example, if the IPM.Note.Meeting.Cancel message class happens to resolve back to IPM.Note, do not assume that all subclasses of IPM.Note should use the icon for IPM.Note.</span></span> 
  

