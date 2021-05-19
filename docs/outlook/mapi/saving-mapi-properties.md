---
title: 保存 MAPI 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ed0c14f9-3dcf-49ad-928e-ba872d4d6b5a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5d4653492028151d7e19a5d5490c8c8949002a4f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425888"
---
# <a name="saving-mapi-properties"></a><span data-ttu-id="8458c-103">保存 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8458c-103">Saving MAPI Properties</span></span>

  
  
<span data-ttu-id="8458c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8458c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8458c-105">许多对象都支持处理事务模型，在稍后提交属性之前，对属性的更改不会永久进行。</span><span class="sxs-lookup"><span data-stu-id="8458c-105">Many objects support a transaction model of processing whereby changes to properties are not made permanent until they are committed at a later time.</span></span> <span data-ttu-id="8458c-106">而对属性的更改由 [IMAPIProp：：SetProps](imapiprop-setprops.md) 和 [IMAPIProp：:D eleteProps](imapiprop-deleteprops.md) 方法处理，而提交步骤由 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md)处理。</span><span class="sxs-lookup"><span data-stu-id="8458c-106">Whereas changes to properties are handled by the [IMAPIProp::SetProps](imapiprop-setprops.md) and [IMAPIProp::DeleteProps](imapiprop-deleteprops.md) methods, the commit step is handled by [IMAPIProp::SaveChanges](imapiprop-savechanges.md).</span></span> <span data-ttu-id="8458c-107">直到成功调用 **SaveChanges** 之后，才能访问对象的属性的最新版本。</span><span class="sxs-lookup"><span data-stu-id="8458c-107">It isn't until after a successful call to **SaveChanges** that the most recent version of an object's properties can be accessed.</span></span> 
  
<span data-ttu-id="8458c-108">当 **SaveChanges** 返回错误值MAPI_E_OBJECT_CHANGED，这是一条警告，提示另一个客户端同时向对象提交更改。</span><span class="sxs-lookup"><span data-stu-id="8458c-108">When **SaveChanges** returns the error value MAPI_E_OBJECT_CHANGED, this is a warning that another client is simultaneously committing changes to the object.</span></span> <span data-ttu-id="8458c-109">多个客户端通过调用其 **OpenEntry** 方法并设置 MAPI_MODIFY 标志，从而成功地打开对象，具体取决于实现对象的提供程序。</span><span class="sxs-lookup"><span data-stu-id="8458c-109">It is possible, depending on the provider implementing the object, for multiple clients to successfully open an object by calling its **OpenEntry** method with the MAPI_MODIFY flag set, giving them read/write access.</span></span> <span data-ttu-id="8458c-110">从此类 **OpenEntry** 调用返回的对象是存储数据的快照。</span><span class="sxs-lookup"><span data-stu-id="8458c-110">The object that is returned from such an **OpenEntry** call is a snapshot of the storage data.</span></span> <span data-ttu-id="8458c-111">每次更改此数据的后续尝试都可能会覆盖上一次尝试。</span><span class="sxs-lookup"><span data-stu-id="8458c-111">Each subsequent attempt to change this data can overwrite the previous attempt.</span></span> 
  
<span data-ttu-id="8458c-112">从 **SaveChanges** MAPI_E_OBJECT_CHANGED时，客户端可以选择：</span><span class="sxs-lookup"><span data-stu-id="8458c-112">Upon receiving MAPI_E_OBJECT_CHANGED from **SaveChanges**, a client has the option to:</span></span> 
  
- <span data-ttu-id="8458c-113">创建对象的副本以保存更改。</span><span class="sxs-lookup"><span data-stu-id="8458c-113">Make a copy of the object to hold the changes.</span></span>
    
- <span data-ttu-id="8458c-114">对 **SaveChanges 进行** 另一个调用，指定FORCE_SAVE。</span><span class="sxs-lookup"><span data-stu-id="8458c-114">Make another call to **SaveChanges**, specifying FORCE_SAVE.</span></span> 
    
<span data-ttu-id="8458c-115">调用具有 FORCE_SAVE 标志的 **SaveChanges** 会覆盖上一次保存，并永久更改客户端。</span><span class="sxs-lookup"><span data-stu-id="8458c-115">Calling **SaveChanges** with the FORCE_SAVE flag overwrites the previous save and makes a client's changes permanent.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8458c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8458c-116">See also</span></span>



[<span data-ttu-id="8458c-117">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="8458c-117">MAPI Property Overview</span></span>](mapi-property-overview.md)

