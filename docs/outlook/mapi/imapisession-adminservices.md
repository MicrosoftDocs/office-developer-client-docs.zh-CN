---
title: IMAPISessionAdminServices
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.AdminServices
api_type:
- COM
ms.assetid: 487fab39-5c2c-4e1a-9f90-4da64f5e198b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 850d4d952102e11d11234fa3184b88e280a98c21
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775571"
---
# <a name="imapisessionadminservices"></a><span data-ttu-id="6dc30-103">IMAPISession::AdminServices</span><span class="sxs-lookup"><span data-stu-id="6dc30-103">IMAPISession::AdminServices</span></span>

  
  
<span data-ttu-id="6dc30-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6dc30-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6dc30-105">返回对消息服务的更改[IMsgServiceAdmin](imsgserviceadminiunknown.md)指针。</span><span class="sxs-lookup"><span data-stu-id="6dc30-105">Returns an [IMsgServiceAdmin](imsgserviceadminiunknown.md) pointer for making changes to message services.</span></span> 
  
```cpp
HRESULT AdminServices(
  ULONG ulFlags,
  LPSERVICEADMIN FAR * lppServiceAdmin
);
```

## <a name="parameters"></a><span data-ttu-id="6dc30-106">参数</span><span class="sxs-lookup"><span data-stu-id="6dc30-106">Parameters</span></span>

 <span data-ttu-id="6dc30-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="6dc30-107">_ulFlags_</span></span>
  
> <span data-ttu-id="6dc30-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="6dc30-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="6dc30-109">_lppServiceAdmin_</span><span class="sxs-lookup"><span data-stu-id="6dc30-109">_lppServiceAdmin_</span></span>
  
> <span data-ttu-id="6dc30-110">[输出]指向与邮件服务管理对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="6dc30-110">[out] A pointer to a pointer to a message service administration object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6dc30-111">返回值</span><span class="sxs-lookup"><span data-stu-id="6dc30-111">Return value</span></span>

<span data-ttu-id="6dc30-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6dc30-112">S_OK</span></span> 
  
> <span data-ttu-id="6dc30-113">已成功返回指向消息服务管理对象的指针。</span><span class="sxs-lookup"><span data-stu-id="6dc30-113">A pointer to a message service administration object was successfully returned.</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="6dc30-114">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="6dc30-114">Notes to callers</span></span>

<span data-ttu-id="6dc30-115">**IMAPISession::AdminServices**方法创建一个邮件服务管理对象，一个对象，支持**IMsgServiceAdmin**接口并返回一个指针。</span><span class="sxs-lookup"><span data-stu-id="6dc30-115">The **IMAPISession::AdminServices** method creates a message service administration object, an object that supports the **IMsgServiceAdmin** interface and returns a pointer.</span></span> <span data-ttu-id="6dc30-116">通过使用此指针，您可以调用**IMsgServiceAdmin**方法来更改任何会话配置文件中的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="6dc30-116">By using this pointer, you can call **IMsgServiceAdmin** methods to change any of the message services in the session profile.</span></span> <span data-ttu-id="6dc30-117">请注意，这些更改才会生效直到下一个会话;当前会话会受到影响。</span><span class="sxs-lookup"><span data-stu-id="6dc30-117">Be aware that these changes do not take effect until the next session; the current session is unaffected.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="6dc30-118">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="6dc30-118">MFCMAPI reference</span></span>

<span data-ttu-id="6dc30-119">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="6dc30-119">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="6dc30-120">**文件**</span><span class="sxs-lookup"><span data-stu-id="6dc30-120">**File**</span></span>|<span data-ttu-id="6dc30-121">**函数**</span><span class="sxs-lookup"><span data-stu-id="6dc30-121">**Function**</span></span>|<span data-ttu-id="6dc30-122">**Comment**</span><span class="sxs-lookup"><span data-stu-id="6dc30-122">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6dc30-123">MAPIStoreFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="6dc30-123">MAPIStoreFunctions.cpp</span></span>  <br/> |<span data-ttu-id="6dc30-124">GetServerName</span><span class="sxs-lookup"><span data-stu-id="6dc30-124">GetServerName</span></span>  <br/> |<span data-ttu-id="6dc30-125">MFCMAPI 使用**IMAPISession::AdminServices**方法来访问的配置文件读取的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="6dc30-125">MFCMAPI uses the **IMAPISession::AdminServices** method to access the profile to read the server name.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6dc30-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6dc30-126">See also</span></span>



[<span data-ttu-id="6dc30-127">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6dc30-127">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)
  
[<span data-ttu-id="6dc30-128">IProfAdmin::AdminServices</span><span class="sxs-lookup"><span data-stu-id="6dc30-128">IProfAdmin::AdminServices</span></span>](iprofadmin-adminservices.md)
  
[<span data-ttu-id="6dc30-129">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6dc30-129">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="6dc30-130">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="6dc30-130">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

