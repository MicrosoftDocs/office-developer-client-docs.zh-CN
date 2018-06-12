---
title: IAttachmentSecurityIsAttachmentBlocked
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAttachmentSecurity.IsAttachmentBlocked
api_type:
- COM
ms.assetid: 6986d27a-9602-e44a-0797-4c47f2184ef7
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: 45e4362fc025c1784e9432c5d641e865a044bd00
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775280"
---
# <a name="iattachmentsecurityisattachmentblocked"></a><span data-ttu-id="95c82-103">IAttachmentSecurity::IsAttachmentBlocked</span><span class="sxs-lookup"><span data-stu-id="95c82-103">IAttachmentSecurity::IsAttachmentBlocked</span></span>

  
  
<span data-ttu-id="95c82-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="95c82-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="95c82-105">检查是否指定的附件阻止通过 Microsoft Outlook 2010 或 Microsoft Outlook 2013 的查看和编制索引。</span><span class="sxs-lookup"><span data-stu-id="95c82-105">Checks if a specified attachment is blocked by Microsoft Outlook 2010 or Microsoft Outlook 2013 for viewing and indexing.</span></span>
  
```cpp
HRESULT IAttachmentSecurity::IsAttachmentBlocked( 
    LPCWSTR pwszFileName,  
    BOOL *pfBlocked 
);
```

## <a name="parameters"></a><span data-ttu-id="95c82-106">参数</span><span class="sxs-lookup"><span data-stu-id="95c82-106">Parameters</span></span>

 <span data-ttu-id="95c82-107">_pwszFileName_</span><span class="sxs-lookup"><span data-stu-id="95c82-107">_pwszFileName_</span></span>
  
> <span data-ttu-id="95c82-108">[in]指向附件的文件名。</span><span class="sxs-lookup"><span data-stu-id="95c82-108">[in] Pointer to the filename of an attachment.</span></span>
    
 <span data-ttu-id="95c82-109">_pfBlocked_</span><span class="sxs-lookup"><span data-stu-id="95c82-109">_pfBlocked_</span></span>
  
> <span data-ttu-id="95c82-110">[输出]为值，该值指示**true**将阻止指定的附件; 如果指针否则为**false**。</span><span class="sxs-lookup"><span data-stu-id="95c82-110">[out] Pointer to a value indicating **true** if the specified attachment is blocked; otherwise, **false**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="95c82-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95c82-111">See also</span></span>



[<span data-ttu-id="95c82-112">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="95c82-112">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="95c82-113">验证被阻止的附件</span><span class="sxs-lookup"><span data-stu-id="95c82-113">Verify an Attachment is Blocked</span></span>](how-to-verify-an-attachment-is-blocked.md)

