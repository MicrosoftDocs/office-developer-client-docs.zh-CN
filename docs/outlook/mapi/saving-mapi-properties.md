---
title: 保存 MAPI 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ed0c14f9-3dcf-49ad-928e-ba872d4d6b5a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5125fc8f3e36087a05802c38127a8402ae67d468
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576300"
---
# <a name="saving-mapi-properties"></a><span data-ttu-id="96a36-103">保存 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="96a36-103">Saving MAPI Properties</span></span>

  
  
<span data-ttu-id="96a36-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="96a36-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="96a36-105">很多对象支持事务处理，对属性的更改不会成为永久性直到提交稍后由此模型。</span><span class="sxs-lookup"><span data-stu-id="96a36-105">Many objects support a transaction model of processing whereby changes to properties are not made permanent until they are committed at a later time.</span></span> <span data-ttu-id="96a36-106">由[IMAPIProp::SetProps](imapiprop-setprops.md)和[IMAPIProp::DeleteProps](imapiprop-deleteprops.md)方法处理对属性的更改，而是由[IMAPIProp::SaveChanges](imapiprop-savechanges.md)处理提交步骤。</span><span class="sxs-lookup"><span data-stu-id="96a36-106">Whereas changes to properties are handled by the [IMAPIProp::SetProps](imapiprop-setprops.md) and [IMAPIProp::DeleteProps](imapiprop-deleteprops.md) methods, the commit step is handled by [IMAPIProp::SaveChanges](imapiprop-savechanges.md).</span></span> <span data-ttu-id="96a36-107">此文件不成功调用**SaveChanges**可访问对象的属性的最新版本之后。</span><span class="sxs-lookup"><span data-stu-id="96a36-107">It isn't until after a successful call to **SaveChanges** that the most recent version of an object's properties can be accessed.</span></span> 
  
<span data-ttu-id="96a36-108">当**SaveChanges**将返回错误值 MAPI_E_OBJECT_CHANGED 时，这是一条警告，另一个客户端同时将对对象提交的更改。</span><span class="sxs-lookup"><span data-stu-id="96a36-108">When **SaveChanges** returns the error value MAPI_E_OBJECT_CHANGED, this is a warning that another client is simultaneously committing changes to the object.</span></span> <span data-ttu-id="96a36-109">有可能，具体取决于提供程序成功实现多个客户端到该对象，通过调用设置了 MAPI_MODIFY 标志其**OpenEntry**方法授予他们读/写访问权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="96a36-109">It is possible, depending on the provider implementing the object, for multiple clients to successfully open an object by calling its **OpenEntry** method with the MAPI_MODIFY flag set, giving them read/write access.</span></span> <span data-ttu-id="96a36-110">返回从例如**OpenEntry**呼叫是存储数据的快照的对象。</span><span class="sxs-lookup"><span data-stu-id="96a36-110">The object that is returned from such an **OpenEntry** call is a snapshot of the storage data.</span></span> <span data-ttu-id="96a36-111">每个后续尝试更改此数据可以覆盖上一次尝试。</span><span class="sxs-lookup"><span data-stu-id="96a36-111">Each subsequent attempt to change this data can overwrite the previous attempt.</span></span> 
  
<span data-ttu-id="96a36-112">在从**SaveChanges**收到 MAPI_E_OBJECT_CHANGED，客户端还提供了选项：</span><span class="sxs-lookup"><span data-stu-id="96a36-112">Upon receiving MAPI_E_OBJECT_CHANGED from **SaveChanges**, a client has the option to:</span></span> 
  
- <span data-ttu-id="96a36-113">创建要保存所做的更改的对象的副本。</span><span class="sxs-lookup"><span data-stu-id="96a36-113">Make a copy of the object to hold the changes.</span></span>
    
- <span data-ttu-id="96a36-114">发起**SaveChanges**，指定 FORCE_SAVE 到另一个呼叫。</span><span class="sxs-lookup"><span data-stu-id="96a36-114">Make another call to **SaveChanges**, specifying FORCE_SAVE.</span></span> 
    
<span data-ttu-id="96a36-115">使用 FORCE_SAVE 标志调用**SaveChanges**覆盖以前保存，并使客户端的更改永久。</span><span class="sxs-lookup"><span data-stu-id="96a36-115">Calling **SaveChanges** with the FORCE_SAVE flag overwrites the previous save and makes a client's changes permanent.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="96a36-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96a36-116">See also</span></span>



[<span data-ttu-id="96a36-117">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="96a36-117">MAPI Property Overview</span></span>](mapi-property-overview.md)

