---
title: IMAPISessionLogoff
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.Logoff
api_type:
- COM
ms.assetid: 93e38f6c-4b67-4f2d-bc94-631efec86852
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 317c3702415ddf30038ccd0d40cdf0f19abc61f8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338106"
---
# <a name="imapisessionlogoff"></a><span data-ttu-id="97e1a-103">IMAPISession::Logoff</span><span class="sxs-lookup"><span data-stu-id="97e1a-103">IMAPISession::Logoff</span></span>

  
  
<span data-ttu-id="97e1a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="97e1a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="97e1a-105">结束 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="97e1a-105">Ends a MAPI session.</span></span>
  
```cpp
HRESULT Logoff(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  ULONG ulReserved
);
```

## <a name="parameters"></a><span data-ttu-id="97e1a-106">参数</span><span class="sxs-lookup"><span data-stu-id="97e1a-106">Parameters</span></span>

 <span data-ttu-id="97e1a-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="97e1a-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="97e1a-108">[in]要显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="97e1a-108">[in] A handle to the parent window of any dialog boxes or windows to be displayed.</span></span> <span data-ttu-id="97e1a-109">如果未设置值标志MAPI_LOGOFF_UI忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="97e1a-109">This parameter is ignored if the MAPI_LOGOFF_UI flag is not set.</span></span>
    
 <span data-ttu-id="97e1a-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="97e1a-110">_ulFlags_</span></span>
  
> <span data-ttu-id="97e1a-111">[in]控制注销操作的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="97e1a-111">[in] A bitmask of flags that control the logoff operation.</span></span> <span data-ttu-id="97e1a-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="97e1a-112">The following flags can be set:</span></span>
    
<span data-ttu-id="97e1a-113">MAPI_LOGOFF_SHARED</span><span class="sxs-lookup"><span data-stu-id="97e1a-113">MAPI_LOGOFF_SHARED</span></span> 
  
> <span data-ttu-id="97e1a-114">如果此会话是共享的，则应该向使用共享会话登录的所有客户端通知正在注销。</span><span class="sxs-lookup"><span data-stu-id="97e1a-114">If this session is shared, all clients that logged on by using the shared session should be notified of the logoff in progress.</span></span> <span data-ttu-id="97e1a-115">客户端应注销。</span><span class="sxs-lookup"><span data-stu-id="97e1a-115">The clients should log off.</span></span> <span data-ttu-id="97e1a-116">使用共享会话的任何客户端都可以设置此标志。</span><span class="sxs-lookup"><span data-stu-id="97e1a-116">Any client that is using the shared session can set this flag.</span></span> <span data-ttu-id="97e1a-117">MAPI_LOGOFF_SHARED会话未共享，则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="97e1a-117">MAPI_LOGOFF_SHARED is ignored if the current session is not shared.</span></span>
    
<span data-ttu-id="97e1a-118">MAPI_LOGOFF_UI</span><span class="sxs-lookup"><span data-stu-id="97e1a-118">MAPI_LOGOFF_UI</span></span> 
  
> <span data-ttu-id="97e1a-119">**注销** 可以在操作期间显示一个对话框，可能会提示用户进行确认。</span><span class="sxs-lookup"><span data-stu-id="97e1a-119">**Logoff** can display a dialog box during the operation, possibly prompting the user for confirmation.</span></span> 
    
 <span data-ttu-id="97e1a-120">_ulReserved_</span><span class="sxs-lookup"><span data-stu-id="97e1a-120">_ulReserved_</span></span>
  
> <span data-ttu-id="97e1a-121">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="97e1a-121">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="97e1a-122">返回值</span><span class="sxs-lookup"><span data-stu-id="97e1a-122">Return value</span></span>

<span data-ttu-id="97e1a-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="97e1a-123">S_OK</span></span> 
  
> <span data-ttu-id="97e1a-124">注销操作成功。</span><span class="sxs-lookup"><span data-stu-id="97e1a-124">The logoff operation was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="97e1a-125">备注</span><span class="sxs-lookup"><span data-stu-id="97e1a-125">Remarks</span></span>

<span data-ttu-id="97e1a-126">**IMAPISession：：Logoff 方法** 结束 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="97e1a-126">The **IMAPISession::Logoff** method ends a MAPI session.</span></span> <span data-ttu-id="97e1a-127">当 **Logoff** 返回时，除 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) 之外的所有方法均无法调用。</span><span class="sxs-lookup"><span data-stu-id="97e1a-127">When **Logoff** returns, none of the methods except for [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) can be called.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="97e1a-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="97e1a-128">Notes to callers</span></span>

<span data-ttu-id="97e1a-129">当 **Logoff** 返回时，通过调用其 **IUnknown：：Release 方法释放会话** 对象。</span><span class="sxs-lookup"><span data-stu-id="97e1a-129">When **Logoff** returns, release the session object by calling its **IUnknown::Release** method.</span></span> 
  
<span data-ttu-id="97e1a-130">有关结束会话的信息，请参阅结束 [MAPI 会话](ending-a-mapi-session.md)。</span><span class="sxs-lookup"><span data-stu-id="97e1a-130">For more information about ending a session, see [Ending a MAPI Session](ending-a-mapi-session.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="97e1a-131">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="97e1a-131">MFCMAPI reference</span></span>

<span data-ttu-id="97e1a-132">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="97e1a-132">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="97e1a-133">**文件**</span><span class="sxs-lookup"><span data-stu-id="97e1a-133">**File**</span></span>|<span data-ttu-id="97e1a-134">**函数**</span><span class="sxs-lookup"><span data-stu-id="97e1a-134">**Function**</span></span>|<span data-ttu-id="97e1a-135">**备注**</span><span class="sxs-lookup"><span data-stu-id="97e1a-135">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="97e1a-136">MAPIObjects.cpp</span><span class="sxs-lookup"><span data-stu-id="97e1a-136">MAPIObjects.cpp</span></span>  <br/> |<span data-ttu-id="97e1a-137">CMapiObjects：：Logoff</span><span class="sxs-lookup"><span data-stu-id="97e1a-137">CMapiObjects::Logoff</span></span>  <br/> |<span data-ttu-id="97e1a-138">MFCMAPI 使用 **IMAPISession：：Logoff** 方法在释放会话之前从会话注销。</span><span class="sxs-lookup"><span data-stu-id="97e1a-138">MFCMAPI uses the **IMAPISession::Logoff** method to log off from the session before releasing it.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="97e1a-139">由于 Microsoft Office Outlook 2007 Service Pack 2、Microsoft Outlook 2010 和 Microsoft Outlook 2013 中引入了快速关闭行为，客户端永远不应将 **MAPI_LOGOFF_SHARED** 参数传递到 [IMAPISession：：Logoff](imapisession-logoff.md)。</span><span class="sxs-lookup"><span data-stu-id="97e1a-139">Due to the fast shutdown behavior introduced in Microsoft Office Outlook 2007 Service Pack 2, Microsoft Outlook 2010, and Microsoft Outlook 2013, clients should never pass the **MAPI_LOGOFF_SHARED** parameter to [IMAPISession::Logoff](imapisession-logoff.md).</span></span> <span data-ttu-id="97e1a-140">传递 **MAPI_LOGOFF_SHARED** 将导致所有 MAPI 客户端开始关闭，并且会发生意外行为。</span><span class="sxs-lookup"><span data-stu-id="97e1a-140">Passing **MAPI_LOGOFF_SHARED** will cause all MAPI clients to begin shutdown and unexpected behavior will occur.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="97e1a-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97e1a-141">See also</span></span>



[<span data-ttu-id="97e1a-142">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="97e1a-142">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="97e1a-143">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="97e1a-143">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="97e1a-144">结束 MAPI 会话</span><span class="sxs-lookup"><span data-stu-id="97e1a-144">Ending a MAPI Session</span></span>](ending-a-mapi-session.md)

