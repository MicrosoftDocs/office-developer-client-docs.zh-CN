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
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: d255d7b6e80fe0c080fa0a27a7976db758a8c2ec
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439777"
---
# <a name="iattachmentsecurityisattachmentblocked"></a><span data-ttu-id="fdd5d-103">IAttachmentSecurity::IsAttachmentBlocked</span><span class="sxs-lookup"><span data-stu-id="fdd5d-103">IAttachmentSecurity::IsAttachmentBlocked</span></span>

  
  
<span data-ttu-id="fdd5d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fdd5d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fdd5d-105">检查指定的附件是否被 microsoft outlook 2010 或 microsoft outlook 2013 阻止, 以供查看和编制索引。</span><span class="sxs-lookup"><span data-stu-id="fdd5d-105">Checks if a specified attachment is blocked by Microsoft Outlook 2010 or Microsoft Outlook 2013 for viewing and indexing.</span></span>
  
```cpp
HRESULT IAttachmentSecurity::IsAttachmentBlocked( 
    LPCWSTR pwszFileName,  
    BOOL *pfBlocked 
);
```

## <a name="parameters"></a><span data-ttu-id="fdd5d-106">参数</span><span class="sxs-lookup"><span data-stu-id="fdd5d-106">Parameters</span></span>

 <span data-ttu-id="fdd5d-107">_pwszFileName_</span><span class="sxs-lookup"><span data-stu-id="fdd5d-107">_pwszFileName_</span></span>
  
> <span data-ttu-id="fdd5d-108">实时指向附件的文件名的指针。</span><span class="sxs-lookup"><span data-stu-id="fdd5d-108">[in] Pointer to the filename of an attachment.</span></span>
    
 <span data-ttu-id="fdd5d-109">_pfBlocked_</span><span class="sxs-lookup"><span data-stu-id="fdd5d-109">_pfBlocked_</span></span>
  
> <span data-ttu-id="fdd5d-110">排除指向一个值的指针, 该值指示如果指定的附件被阻止, 则为**true** ;否则**为 false**。</span><span class="sxs-lookup"><span data-stu-id="fdd5d-110">[out] Pointer to a value indicating **true** if the specified attachment is blocked; otherwise, **false**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fdd5d-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fdd5d-111">See also</span></span>



[<span data-ttu-id="fdd5d-112">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="fdd5d-112">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="fdd5d-113">验证附件是否已被阻止</span><span class="sxs-lookup"><span data-stu-id="fdd5d-113">Verify an Attachment is Blocked</span></span>](how-to-verify-an-attachment-is-blocked.md)

