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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 91985d3dc8a7816c3da3215e505097c57c63e035
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407569"
---
# <a name="ipersistmessageisdirty"></a><span data-ttu-id="5cff1-103">IPersistMessage::IsDirty</span><span class="sxs-lookup"><span data-stu-id="5cff1-103">IPersistMessage::IsDirty</span></span>

  
  
<span data-ttu-id="5cff1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5cff1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5cff1-105">检查表单中自上次保存以来所做的更改。</span><span class="sxs-lookup"><span data-stu-id="5cff1-105">Checks the form for changes that were made since the last save.</span></span>
  
```cpp
HRESULT IsDirty( void );
```

## <a name="parameters"></a><span data-ttu-id="5cff1-106">参数</span><span class="sxs-lookup"><span data-stu-id="5cff1-106">Parameters</span></span>

<span data-ttu-id="5cff1-107">无</span><span class="sxs-lookup"><span data-stu-id="5cff1-107">None</span></span>
  
## <a name="return-value"></a><span data-ttu-id="5cff1-108">返回值</span><span class="sxs-lookup"><span data-stu-id="5cff1-108">Return value</span></span>

<span data-ttu-id="5cff1-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="5cff1-109">S_OK</span></span> 
  
> <span data-ttu-id="5cff1-110">表单具有自上次保存以来所做的更改。</span><span class="sxs-lookup"><span data-stu-id="5cff1-110">The form has changes that were made since it was last saved.</span></span>
    
<span data-ttu-id="5cff1-111">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5cff1-111">S_FALSE</span></span> 
  
> <span data-ttu-id="5cff1-112">表单没有自上次保存以来所做的更改。</span><span class="sxs-lookup"><span data-stu-id="5cff1-112">The form does not have changes that were made since it was last saved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5cff1-113">备注</span><span class="sxs-lookup"><span data-stu-id="5cff1-113">Remarks</span></span>

<span data-ttu-id="5cff1-114">表单查看器调用 **IPersistMessage：：IsDirty** 方法以确定邮件是否包含未保存的数据。</span><span class="sxs-lookup"><span data-stu-id="5cff1-114">Form viewers call the **IPersistMessage::IsDirty** method to determine whether the message has unsaved data.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5cff1-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5cff1-115">See also</span></span>



[<span data-ttu-id="5cff1-116">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5cff1-116">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)

