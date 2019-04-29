---
title: IABLogonLogoff
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.Logoff
api_type:
- COM
ms.assetid: a36465e2-7be9-4bd6-8091-685f0a045aa9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: af3c1f5135e90274c0251c5a0addf339c14f36c0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416396"
---
# <a name="iablogonlogoff"></a><span data-ttu-id="fcf52-103">IABLogon::Logoff</span><span class="sxs-lookup"><span data-stu-id="fcf52-103">IABLogon::Logoff</span></span>

  
  
<span data-ttu-id="fcf52-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fcf52-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fcf52-105">启动注销过程。</span><span class="sxs-lookup"><span data-stu-id="fcf52-105">Initiates the logoff process.</span></span>
  
```cpp
HRESULT Logoff(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="fcf52-106">参数</span><span class="sxs-lookup"><span data-stu-id="fcf52-106">Parameters</span></span>

 <span data-ttu-id="fcf52-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="fcf52-107">_ulFlags_</span></span>
  
> <span data-ttu-id="fcf52-108">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="fcf52-108">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="fcf52-109">返回值</span><span class="sxs-lookup"><span data-stu-id="fcf52-109">Return value</span></span>

<span data-ttu-id="fcf52-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fcf52-110">S_OK</span></span> 
  
> <span data-ttu-id="fcf52-111">已成功启动注销过程。</span><span class="sxs-lookup"><span data-stu-id="fcf52-111">The logoff process was successfully initiated.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fcf52-112">说明</span><span class="sxs-lookup"><span data-stu-id="fcf52-112">Remarks</span></span>

<span data-ttu-id="fcf52-113">注销过程通常在客户端调用[IMAPISession:: 注销](imapisession-logoff.md)方法结束会话时启动。</span><span class="sxs-lookup"><span data-stu-id="fcf52-113">The logoff process is typically started when a client calls the [IMAPISession::Logoff](imapisession-logoff.md) method to end a session.</span></span> <span data-ttu-id="fcf52-114">然后, MAPI 会调用每个通讯簿提供程序的**IABLogon:: 注销**方法, 以启动注销过程。</span><span class="sxs-lookup"><span data-stu-id="fcf52-114">MAPI then calls each address book provider's **IABLogon::Logoff** method to start the logoff process.</span></span> 
  
<span data-ttu-id="fcf52-115">**IABLogon:: 注销**方法执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="fcf52-115">The **IABLogon::Logoff** method does the following:</span></span> 
  
- <span data-ttu-id="fcf52-116">释放所有打开的对象, 例如任意子对象或 status 对象。</span><span class="sxs-lookup"><span data-stu-id="fcf52-116">Releases all open objects, such as any subobjects or the status object.</span></span>
    
- <span data-ttu-id="fcf52-117">释放提供程序的支持对象。</span><span class="sxs-lookup"><span data-stu-id="fcf52-117">Releases the provider's support object.</span></span>
    
<span data-ttu-id="fcf52-118">有关通讯簿提供程序的注销过程的详细信息, 请参阅[关闭服务提供程序](shutting-down-a-service-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="fcf52-118">For more information about the logoff process of address book providers, see [Shutting Down a Service Provider](shutting-down-a-service-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fcf52-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fcf52-119">See also</span></span>



[<span data-ttu-id="fcf52-120">IABProvider::Logon</span><span class="sxs-lookup"><span data-stu-id="fcf52-120">IABProvider::Logon</span></span>](iabprovider-logon.md)
  
[<span data-ttu-id="fcf52-121">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="fcf52-121">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

