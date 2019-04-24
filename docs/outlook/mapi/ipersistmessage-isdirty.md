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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309609"
---
# <a name="ipersistmessageisdirty"></a><span data-ttu-id="d3614-103">IPersistMessage::IsDirty</span><span class="sxs-lookup"><span data-stu-id="d3614-103">IPersistMessage::IsDirty</span></span>

  
  
<span data-ttu-id="d3614-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d3614-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d3614-105">检查表单的上次保存以来所做的更改。</span><span class="sxs-lookup"><span data-stu-id="d3614-105">Checks the form for changes that were made since the last save.</span></span>
  
```cpp
HRESULT IsDirty( void );
```

## <a name="parameters"></a><span data-ttu-id="d3614-106">参数</span><span class="sxs-lookup"><span data-stu-id="d3614-106">Parameters</span></span>

<span data-ttu-id="d3614-107">无</span><span class="sxs-lookup"><span data-stu-id="d3614-107">None</span></span>
  
## <a name="return-value"></a><span data-ttu-id="d3614-108">返回值</span><span class="sxs-lookup"><span data-stu-id="d3614-108">Return value</span></span>

<span data-ttu-id="d3614-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="d3614-109">S_OK</span></span> 
  
> <span data-ttu-id="d3614-110">表单包含自上次保存以来所做的更改。</span><span class="sxs-lookup"><span data-stu-id="d3614-110">The form has changes that were made since it was last saved.</span></span>
    
<span data-ttu-id="d3614-111">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d3614-111">S_FALSE</span></span> 
  
> <span data-ttu-id="d3614-112">表单不包含自上次保存以来所做的更改。</span><span class="sxs-lookup"><span data-stu-id="d3614-112">The form does not have changes that were made since it was last saved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d3614-113">注解</span><span class="sxs-lookup"><span data-stu-id="d3614-113">Remarks</span></span>

<span data-ttu-id="d3614-114">表单查看者调用**IPersistMessage:: IsDirty**方法, 以确定邮件是否有未保存的数据。</span><span class="sxs-lookup"><span data-stu-id="d3614-114">Form viewers call the **IPersistMessage::IsDirty** method to determine whether the message has unsaved data.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d3614-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3614-115">See also</span></span>



[<span data-ttu-id="d3614-116">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d3614-116">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)

