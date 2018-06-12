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
ms.openlocfilehash: e748427b39418a80cae88e98b4aa7eef6df24393
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775989"
---
# <a name="ipersistmessageisdirty"></a><span data-ttu-id="1ef20-103">IPersistMessage::IsDirty</span><span class="sxs-lookup"><span data-stu-id="1ef20-103">IPersistMessage::IsDirty</span></span>

  
  
<span data-ttu-id="1ef20-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1ef20-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1ef20-105">检查自上次保存以来所做的更改的表单。</span><span class="sxs-lookup"><span data-stu-id="1ef20-105">Checks the form for changes that were made since the last save.</span></span>
  
```cpp
HRESULT IsDirty( void );
```

## <a name="parameters"></a><span data-ttu-id="1ef20-106">参数</span><span class="sxs-lookup"><span data-stu-id="1ef20-106">Parameters</span></span>

<span data-ttu-id="1ef20-107">无</span><span class="sxs-lookup"><span data-stu-id="1ef20-107">None</span></span>
  
## <a name="return-value"></a><span data-ttu-id="1ef20-108">返回值</span><span class="sxs-lookup"><span data-stu-id="1ef20-108">Return value</span></span>

<span data-ttu-id="1ef20-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="1ef20-109">S_OK</span></span> 
  
> <span data-ttu-id="1ef20-110">窗体有自上次保存以来所做的更改。</span><span class="sxs-lookup"><span data-stu-id="1ef20-110">The form has changes that were made since it was last saved.</span></span>
    
<span data-ttu-id="1ef20-111">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="1ef20-111">S_FALSE</span></span> 
  
> <span data-ttu-id="1ef20-112">窗体不具有自上次保存以来所做的更改。</span><span class="sxs-lookup"><span data-stu-id="1ef20-112">The form does not have changes that were made since it was last saved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1ef20-113">备注</span><span class="sxs-lookup"><span data-stu-id="1ef20-113">Remarks</span></span>

<span data-ttu-id="1ef20-114">表单查看器调用**IPersistMessage::IsDirty**方法以确定是否邮件有未保存的数据。</span><span class="sxs-lookup"><span data-stu-id="1ef20-114">Form viewers call the **IPersistMessage::IsDirty** method to determine whether the message has unsaved data.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1ef20-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ef20-115">See also</span></span>



[<span data-ttu-id="1ef20-116">IPersistMessage: IUnknown</span><span class="sxs-lookup"><span data-stu-id="1ef20-116">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)

