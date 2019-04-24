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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337042"
---
# <a name="displaying-form-icons"></a><span data-ttu-id="b4a78-103">显示表单图标</span><span class="sxs-lookup"><span data-stu-id="b4a78-103">Displaying Form Icons</span></span>

  
  
<span data-ttu-id="b4a78-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b4a78-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b4a78-105">在文件夹中显示邮件列表时, 如果通过标准 IPM 中的自定义邮件类区分邮件, 则对用户很有帮助。注释消息。</span><span class="sxs-lookup"><span data-stu-id="b4a78-105">When displaying a list of messages in a folder, it is helpful to your users if you distinguish messages with custom message classes from the standard IPM.Note messages.</span></span> <span data-ttu-id="b4a78-106">自定义邮件类对应于表单服务器, 窗体服务器提供图标来代表自己。</span><span class="sxs-lookup"><span data-stu-id="b4a78-106">Custom message classes correspond to form servers, and form servers provide icons to represent themselves.</span></span> <span data-ttu-id="b4a78-107">您可以在消息列表中显示这些图标, 以便在用户打开邮件之前向每个邮件的邮件类别发出警告。</span><span class="sxs-lookup"><span data-stu-id="b4a78-107">You can display these icons in the list of messages to alert users to each message's message class before the user opens the messages.</span></span> <span data-ttu-id="b4a78-108">通常情况下, 表单的**PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性中的图标是应显示在邮件列表中的图标。</span><span class="sxs-lookup"><span data-stu-id="b4a78-108">Typically, the icon in the form's **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) property is the one that should be displayed in the list of messages.</span></span> <span data-ttu-id="b4a78-109">窗体还具有**PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) 属性, 当窗体在属性表中最小化时, 可以显示该属性。</span><span class="sxs-lookup"><span data-stu-id="b4a78-109">Forms also have a **PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) property that can be displayed when the form is minimized in a property sheet.</span></span>
  
 <span data-ttu-id="b4a78-110">**为邮件类获取一个图标, 而不为该邮件类激活窗体服务器**</span><span class="sxs-lookup"><span data-stu-id="b4a78-110">**To get an icon for a message class without activating the form server for that message class**</span></span>
  
1. <span data-ttu-id="b4a78-111">调用[IMAPIFormMgr:: OpenFormContainer](imapiformmgr-openformcontainer.md)方法以获取指向[IMAPIFormContainer: IUnknown](imapiformcontaineriunknown.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="b4a78-111">Call the [IMAPIFormMgr::OpenFormContainer](imapiformmgr-openformcontainer.md) method to get a pointer to an [IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md) interface.</span></span> 
    
2. <span data-ttu-id="b4a78-112">调用[IMAPIFormContainer:: ResolveMessageClass](imapiformcontainer-resolvemessageclass.md)方法以获取指向[IMAPIFormInfo: IMAPIProp](imapiforminfoimapiprop.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="b4a78-112">Call the [IMAPIFormContainer::ResolveMessageClass](imapiformcontainer-resolvemessageclass.md) method to get a pointer to an [IMAPIFormInfo : IMAPIProp](imapiforminfoimapiprop.md) interface.</span></span> 
    
3. <span data-ttu-id="b4a78-113">调用[IMAPIFormInfo:: MakeIconFromBinary](imapiforminfo-makeiconfrombinary.md)方法以获取图标句柄。</span><span class="sxs-lookup"><span data-stu-id="b4a78-113">Call the [IMAPIFormInfo::MakeIconFromBinary](imapiforminfo-makeiconfrombinary.md) method to get an icon handle.</span></span> 
    
<span data-ttu-id="b4a78-114">然后, 可以使用标准 Win32 api 显示图标。</span><span class="sxs-lookup"><span data-stu-id="b4a78-114">The icon can then be displayed using standard Win32 APIs.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b4a78-115">拥有邮件类别的图标后, 请尽一切努力缓存该图标。</span><span class="sxs-lookup"><span data-stu-id="b4a78-115">Once you have the icon for a message class, make every effort to cache that icon.</span></span> <span data-ttu-id="b4a78-116">不缓存图标会严重影响客户端应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="b4a78-116">Not caching icons severely affects the performance of client applications.</span></span> <span data-ttu-id="b4a78-117">缓存图标时, 请注意邮件类与其子类之间的关系。</span><span class="sxs-lookup"><span data-stu-id="b4a78-117">When caching icons, be careful of the relationships between message classes and their subclasses.</span></span> <span data-ttu-id="b4a78-118">例如, 如果 IPM。注释。若要解决此问题, 请执行 "取消邮件类" 操作。注意, 不要假定所有的 IPM 子类别。注意应使用 IPM 的图标。便笺.</span><span class="sxs-lookup"><span data-stu-id="b4a78-118">For example, if the IPM.Note.Meeting.Cancel message class happens to resolve back to IPM.Note, do not assume that all subclasses of IPM.Note should use the icon for IPM.Note.</span></span> 
  

