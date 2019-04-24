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
ms.openlocfilehash: c639523a02047bf00c378dafd7bc698d7d4e5fff
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322412"
---
# <a name="imapisessionadminservices"></a><span data-ttu-id="b2e9b-103">IMAPISession::AdminServices</span><span class="sxs-lookup"><span data-stu-id="b2e9b-103">IMAPISession::AdminServices</span></span>

  
  
<span data-ttu-id="b2e9b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b2e9b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b2e9b-105">返回用于对邮件服务进行更改的[IMsgServiceAdmin](imsgserviceadminiunknown.md)指针。</span><span class="sxs-lookup"><span data-stu-id="b2e9b-105">Returns an [IMsgServiceAdmin](imsgserviceadminiunknown.md) pointer for making changes to message services.</span></span> 
  
```cpp
HRESULT AdminServices(
  ULONG ulFlags,
  LPSERVICEADMIN FAR * lppServiceAdmin
);
```

## <a name="parameters"></a><span data-ttu-id="b2e9b-106">参数</span><span class="sxs-lookup"><span data-stu-id="b2e9b-106">Parameters</span></span>

 <span data-ttu-id="b2e9b-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b2e9b-107">_ulFlags_</span></span>
  
> <span data-ttu-id="b2e9b-108">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="b2e9b-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="b2e9b-109">_lppServiceAdmin_</span><span class="sxs-lookup"><span data-stu-id="b2e9b-109">_lppServiceAdmin_</span></span>
  
> <span data-ttu-id="b2e9b-110">排除指向邮件服务管理对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="b2e9b-110">[out] A pointer to a pointer to a message service administration object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b2e9b-111">返回值</span><span class="sxs-lookup"><span data-stu-id="b2e9b-111">Return value</span></span>

<span data-ttu-id="b2e9b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2e9b-112">S_OK</span></span> 
  
> <span data-ttu-id="b2e9b-113">成功返回了指向邮件服务管理对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b2e9b-113">A pointer to a message service administration object was successfully returned.</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="b2e9b-114">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="b2e9b-114">Notes to callers</span></span>

<span data-ttu-id="b2e9b-115">**IMAPISession:: AdminServices**方法创建一个邮件服务管理对象, 该对象是一个支持**IMsgServiceAdmin**接口的对象, 并返回一个指针。</span><span class="sxs-lookup"><span data-stu-id="b2e9b-115">The **IMAPISession::AdminServices** method creates a message service administration object, an object that supports the **IMsgServiceAdmin** interface and returns a pointer.</span></span> <span data-ttu-id="b2e9b-116">通过使用此指针, 可以调用**IMsgServiceAdmin**方法来更改会话配置文件中的任何邮件服务。</span><span class="sxs-lookup"><span data-stu-id="b2e9b-116">By using this pointer, you can call **IMsgServiceAdmin** methods to change any of the message services in the session profile.</span></span> <span data-ttu-id="b2e9b-117">请注意, 这些更改在下次会话之前不会生效;当前会话不受影响。</span><span class="sxs-lookup"><span data-stu-id="b2e9b-117">Be aware that these changes do not take effect until the next session; the current session is unaffected.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="b2e9b-118">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="b2e9b-118">MFCMAPI reference</span></span>

<span data-ttu-id="b2e9b-119">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="b2e9b-119">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="b2e9b-120">**文件**</span><span class="sxs-lookup"><span data-stu-id="b2e9b-120">**File**</span></span>|<span data-ttu-id="b2e9b-121">**函数**</span><span class="sxs-lookup"><span data-stu-id="b2e9b-121">**Function**</span></span>|<span data-ttu-id="b2e9b-122">**备注**</span><span class="sxs-lookup"><span data-stu-id="b2e9b-122">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b2e9b-123">MAPIStoreFunctions</span><span class="sxs-lookup"><span data-stu-id="b2e9b-123">MAPIStoreFunctions.cpp</span></span>  <br/> |<span data-ttu-id="b2e9b-124">GetServerName</span><span class="sxs-lookup"><span data-stu-id="b2e9b-124">GetServerName</span></span>  <br/> |<span data-ttu-id="b2e9b-125">MFCMAPI 使用**IMAPISession:: AdminServices**方法访问配置文件以读取服务器名称。</span><span class="sxs-lookup"><span data-stu-id="b2e9b-125">MFCMAPI uses the **IMAPISession::AdminServices** method to access the profile to read the server name.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b2e9b-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2e9b-126">See also</span></span>



[<span data-ttu-id="b2e9b-127">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b2e9b-127">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)
  
[<span data-ttu-id="b2e9b-128">IProfAdmin::AdminServices</span><span class="sxs-lookup"><span data-stu-id="b2e9b-128">IProfAdmin::AdminServices</span></span>](iprofadmin-adminservices.md)
  
[<span data-ttu-id="b2e9b-129">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b2e9b-129">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="b2e9b-130">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="b2e9b-130">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

