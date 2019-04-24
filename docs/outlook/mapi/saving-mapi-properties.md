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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283084"
---
# <a name="saving-mapi-properties"></a><span data-ttu-id="96731-103">保存 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="96731-103">Saving MAPI Properties</span></span>

  
  
<span data-ttu-id="96731-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="96731-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="96731-105">许多对象支持处理的事务模型, 对属性所做的更改不会永久成为永久更改, 除非在以后提交它们。</span><span class="sxs-lookup"><span data-stu-id="96731-105">Many objects support a transaction model of processing whereby changes to properties are not made permanent until they are committed at a later time.</span></span> <span data-ttu-id="96731-106">而对属性的更改由[IMAPIProp:: SetProps](imapiprop-setprops.md)和[IMAPIProp::D eleteprops](imapiprop-deleteprops.md)方法处理, 则 commit 步骤将由[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)处理。</span><span class="sxs-lookup"><span data-stu-id="96731-106">Whereas changes to properties are handled by the [IMAPIProp::SetProps](imapiprop-setprops.md) and [IMAPIProp::DeleteProps](imapiprop-deleteprops.md) methods, the commit step is handled by [IMAPIProp::SaveChanges](imapiprop-savechanges.md).</span></span> <span data-ttu-id="96731-107">在成功调用某个对象的属性的\*\*\*\* 最新版本之前, 此方法不会一直发生。</span><span class="sxs-lookup"><span data-stu-id="96731-107">It isn't until after a successful call to **SaveChanges** that the most recent version of an object's properties can be accessed.</span></span> 
  
<span data-ttu-id="96731-108">当**SaveChanges**返回错误值 MAPI_E_OBJECT_CHANGED 时, 这是一个警告, 指出另一个客户端同时提交对该对象的更改。</span><span class="sxs-lookup"><span data-stu-id="96731-108">When **SaveChanges** returns the error value MAPI_E_OBJECT_CHANGED, this is a warning that another client is simultaneously committing changes to the object.</span></span> <span data-ttu-id="96731-109">根据实现对象的提供程序的不同, 多个客户端可以通过调用其**OpenEntry**方法并设置 MAPI_MODIFY 标志来成功打开对象, 从而为它们提供读/写访问权限。</span><span class="sxs-lookup"><span data-stu-id="96731-109">It is possible, depending on the provider implementing the object, for multiple clients to successfully open an object by calling its **OpenEntry** method with the MAPI_MODIFY flag set, giving them read/write access.</span></span> <span data-ttu-id="96731-110">从这样的**OpenEntry**调用返回的对象是存储数据的快照。</span><span class="sxs-lookup"><span data-stu-id="96731-110">The object that is returned from such an **OpenEntry** call is a snapshot of the storage data.</span></span> <span data-ttu-id="96731-111">随后每次尝试更改此数据时, 都可能会覆盖之前的尝试。</span><span class="sxs-lookup"><span data-stu-id="96731-111">Each subsequent attempt to change this data can overwrite the previous attempt.</span></span> 
  
<span data-ttu-id="96731-112">在从**SaveChanges**接收 MAPI_E_OBJECT_CHANGED 时, 客户端可以选择执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="96731-112">Upon receiving MAPI_E_OBJECT_CHANGED from **SaveChanges**, a client has the option to:</span></span> 
  
- <span data-ttu-id="96731-113">创建对象的副本以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="96731-113">Make a copy of the object to hold the changes.</span></span>
    
- <span data-ttu-id="96731-114">对**SaveChanges**调用另一个调用, 指定 FORCE_SAVE。</span><span class="sxs-lookup"><span data-stu-id="96731-114">Make another call to **SaveChanges**, specifying FORCE_SAVE.</span></span> 
    
<span data-ttu-id="96731-115">使用 FORCE_SAVE 标志调用**SaveChanges**将覆盖上一次保存, 并使客户端的更改永久化。</span><span class="sxs-lookup"><span data-stu-id="96731-115">Calling **SaveChanges** with the FORCE_SAVE flag overwrites the previous save and makes a client's changes permanent.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="96731-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96731-116">See also</span></span>



[<span data-ttu-id="96731-117">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="96731-117">MAPI Property Overview</span></span>](mapi-property-overview.md)

