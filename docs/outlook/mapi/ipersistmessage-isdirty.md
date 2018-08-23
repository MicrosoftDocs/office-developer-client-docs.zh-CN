---
title: IPersistMessageIsDirty
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage.IsDirty
api_type:
- COM
ms.assetid: 57f688db-3a1c-49ff-a15a-8508bda5de68
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0d2ae556f4dd98b5f6e274a21c608d4ea364d4ec
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576202"
---
# <a name="ipersistmessageisdirty"></a><span data-ttu-id="231ac-103">IPersistMessage::IsDirty</span><span class="sxs-lookup"><span data-stu-id="231ac-103">IPersistMessage::IsDirty</span></span>

  
  
<span data-ttu-id="231ac-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="231ac-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="231ac-105">检查自上次保存以来所做的更改的表单。</span><span class="sxs-lookup"><span data-stu-id="231ac-105">Checks the form for changes that were made since the last save.</span></span>
  
```cpp
HRESULT IsDirty( void );
```

## <a name="parameters"></a><span data-ttu-id="231ac-106">参数</span><span class="sxs-lookup"><span data-stu-id="231ac-106">Parameters</span></span>

<span data-ttu-id="231ac-107">无</span><span class="sxs-lookup"><span data-stu-id="231ac-107">None</span></span>
  
## <a name="return-value"></a><span data-ttu-id="231ac-108">返回值</span><span class="sxs-lookup"><span data-stu-id="231ac-108">Return value</span></span>

<span data-ttu-id="231ac-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="231ac-109">S_OK</span></span> 
  
> <span data-ttu-id="231ac-110">窗体有自上次保存以来所做的更改。</span><span class="sxs-lookup"><span data-stu-id="231ac-110">The form has changes that were made since it was last saved.</span></span>
    
<span data-ttu-id="231ac-111">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="231ac-111">S_FALSE</span></span> 
  
> <span data-ttu-id="231ac-112">窗体不具有自上次保存以来所做的更改。</span><span class="sxs-lookup"><span data-stu-id="231ac-112">The form does not have changes that were made since it was last saved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="231ac-113">注解</span><span class="sxs-lookup"><span data-stu-id="231ac-113">Remarks</span></span>

<span data-ttu-id="231ac-114">表单查看器调用**IPersistMessage::IsDirty**方法以确定是否邮件有未保存的数据。</span><span class="sxs-lookup"><span data-stu-id="231ac-114">Form viewers call the **IPersistMessage::IsDirty** method to determine whether the message has unsaved data.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="231ac-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="231ac-115">See also</span></span>



[<span data-ttu-id="231ac-116">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="231ac-116">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)

