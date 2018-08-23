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
ms.openlocfilehash: ff13866139bf422f071eaba2c146aa1140ccd1ab
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565044"
---
# <a name="iattachmentsecurityisattachmentblocked"></a><span data-ttu-id="8bd9d-103">IAttachmentSecurity::IsAttachmentBlocked</span><span class="sxs-lookup"><span data-stu-id="8bd9d-103">IAttachmentSecurity::IsAttachmentBlocked</span></span>

  
  
<span data-ttu-id="8bd9d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8bd9d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8bd9d-105">检查是否指定的附件阻止通过 Microsoft Outlook 2010 或 Microsoft Outlook 2013 的查看和编制索引。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-105">Checks if a specified attachment is blocked by Microsoft Outlook 2010 or Microsoft Outlook 2013 for viewing and indexing.</span></span>
  
```cpp
HRESULT IAttachmentSecurity::IsAttachmentBlocked( 
    LPCWSTR pwszFileName,  
    BOOL *pfBlocked 
);
```

## <a name="parameters"></a><span data-ttu-id="8bd9d-106">参数</span><span class="sxs-lookup"><span data-stu-id="8bd9d-106">Parameters</span></span>

 <span data-ttu-id="8bd9d-107">_pwszFileName_</span><span class="sxs-lookup"><span data-stu-id="8bd9d-107">_pwszFileName_</span></span>
  
> <span data-ttu-id="8bd9d-108">[in]指向附件的文件名。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-108">[in] Pointer to the filename of an attachment.</span></span>
    
 <span data-ttu-id="8bd9d-109">_pfBlocked_</span><span class="sxs-lookup"><span data-stu-id="8bd9d-109">_pfBlocked_</span></span>
  
> <span data-ttu-id="8bd9d-110">[输出]为值，该值指示**true**将阻止指定的附件; 如果指针否则为**false**。</span><span class="sxs-lookup"><span data-stu-id="8bd9d-110">[out] Pointer to a value indicating **true** if the specified attachment is blocked; otherwise, **false**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8bd9d-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8bd9d-111">See also</span></span>



[<span data-ttu-id="8bd9d-112">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="8bd9d-112">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="8bd9d-113">验证附件是否已遭阻止</span><span class="sxs-lookup"><span data-stu-id="8bd9d-113">Verify an Attachment is Blocked</span></span>](how-to-verify-an-attachment-is-blocked.md)

