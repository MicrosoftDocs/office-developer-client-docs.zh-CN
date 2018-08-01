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
ms.openlocfilehash: 7d6ccd64fea0af30e81a2db0bcb9630062b4b64d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775551"
---
# <a name="imapisessionlogoff"></a><span data-ttu-id="ac6e5-103">IMAPISession::Logoff</span><span class="sxs-lookup"><span data-stu-id="ac6e5-103">IMAPISession::Logoff</span></span>

  
  
<span data-ttu-id="ac6e5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ac6e5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ac6e5-105">结束 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-105">Ends a MAPI session.</span></span>
  
```cpp
HRESULT Logoff(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  ULONG ulReserved
);
```

## <a name="parameters"></a><span data-ttu-id="ac6e5-106">参数</span><span class="sxs-lookup"><span data-stu-id="ac6e5-106">Parameters</span></span>

 <span data-ttu-id="ac6e5-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="ac6e5-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="ac6e5-108">[in]父窗口的任何对话框或窗口将显示句柄。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-108">[in] A handle to the parent window of any dialog boxes or windows to be displayed.</span></span> <span data-ttu-id="ac6e5-109">如果未设置 MAPI_LOGOFF_UI 标志，则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-109">This parameter is ignored if the MAPI_LOGOFF_UI flag is not set.</span></span>
    
 <span data-ttu-id="ac6e5-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ac6e5-110">_ulFlags_</span></span>
  
> <span data-ttu-id="ac6e5-111">[in]控制注销操作的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-111">[in] A bitmask of flags that control the logoff operation.</span></span> <span data-ttu-id="ac6e5-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="ac6e5-112">The following flags can be set:</span></span>
    
<span data-ttu-id="ac6e5-113">MAPI_LOGOFF_SHARED</span><span class="sxs-lookup"><span data-stu-id="ac6e5-113">MAPI_LOGOFF_SHARED</span></span> 
  
> <span data-ttu-id="ac6e5-114">如果共享此会话，则登录使用共享的会话的所有客户端应正在注销的通知。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-114">If this session is shared, all clients that logged on by using the shared session should be notified of the logoff in progress.</span></span> <span data-ttu-id="ac6e5-115">客户端应注销。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-115">The clients should log off.</span></span> <span data-ttu-id="ac6e5-116">使用共享的会话的任何客户端可以设置此标志。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-116">Any client that is using the shared session can set this flag.</span></span> <span data-ttu-id="ac6e5-117">如果不共享当前会话，则忽略 MAPI_LOGOFF_SHARED。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-117">MAPI_LOGOFF_SHARED is ignored if the current session is not shared.</span></span>
    
<span data-ttu-id="ac6e5-118">MAPI_LOGOFF_UI</span><span class="sxs-lookup"><span data-stu-id="ac6e5-118">MAPI_LOGOFF_UI</span></span> 
  
> <span data-ttu-id="ac6e5-119">**注销**可以显示一个对话框，在操作时，可能会提示用户进行确认。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-119">**Logoff** can display a dialog box during the operation, possibly prompting the user for confirmation.</span></span> 
    
 <span data-ttu-id="ac6e5-120">_ulReserved_</span><span class="sxs-lookup"><span data-stu-id="ac6e5-120">_ulReserved_</span></span>
  
> <span data-ttu-id="ac6e5-121">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-121">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ac6e5-122">返回值</span><span class="sxs-lookup"><span data-stu-id="ac6e5-122">Return value</span></span>

<span data-ttu-id="ac6e5-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac6e5-123">S_OK</span></span> 
  
> <span data-ttu-id="ac6e5-124">注销操作已成功。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-124">The logoff operation was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ac6e5-125">说明</span><span class="sxs-lookup"><span data-stu-id="ac6e5-125">Remarks</span></span>

<span data-ttu-id="ac6e5-126">**IMAPISession::Logoff**方法结束 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-126">The **IMAPISession::Logoff** method ends a MAPI session.</span></span> <span data-ttu-id="ac6e5-127">**注销**返回时，无除外[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法可调用它。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-127">When **Logoff** returns, none of the methods except for [IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx) can be called.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="ac6e5-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="ac6e5-128">Notes to callers</span></span>

<span data-ttu-id="ac6e5-129">**注销**返回时，通过调用其**IUnknown::Release**方法释放会话对象。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-129">When **Logoff** returns, release the session object by calling its **IUnknown::Release** method.</span></span> 
  
<span data-ttu-id="ac6e5-130">结束会话的详细信息，请参阅[结束 MAPI 会话](ending-a-mapi-session.md)。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-130">For more information about ending a session, see [Ending a MAPI Session](ending-a-mapi-session.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="ac6e5-131">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="ac6e5-131">MFCMAPI reference</span></span>

<span data-ttu-id="ac6e5-132">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-132">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="ac6e5-133">**文件**</span><span class="sxs-lookup"><span data-stu-id="ac6e5-133">**File**</span></span>|<span data-ttu-id="ac6e5-134">**函数**</span><span class="sxs-lookup"><span data-stu-id="ac6e5-134">**Function**</span></span>|<span data-ttu-id="ac6e5-135">**Comment**</span><span class="sxs-lookup"><span data-stu-id="ac6e5-135">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ac6e5-136">MAPIObjects.cpp</span><span class="sxs-lookup"><span data-stu-id="ac6e5-136">MAPIObjects.cpp</span></span>  <br/> |<span data-ttu-id="ac6e5-137">CMapiObjects::Logoff</span><span class="sxs-lookup"><span data-stu-id="ac6e5-137">CMapiObjects::Logoff</span></span>  <br/> |<span data-ttu-id="ac6e5-138">MFCMAPI 使用**IMAPISession::Logoff**方法从之前将其释放会话中注销。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-138">MFCMAPI uses the **IMAPISession::Logoff** method to log off from the session before releasing it.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="ac6e5-139">在 Microsoft Office Outlook 2007 Service Pack 2、 Microsoft Outlook 2010 和 Microsoft Outlook 2013 中引入的快速关闭行为，由于客户端应永远不会传递给[IMAPISession::Logoff](imapisession-logoff.md)的**MAPI_LOGOFF_SHARED**参数。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-139">Due to the fast shutdown behavior introduced in Microsoft Office Outlook 2007 Service Pack 2, Microsoft Outlook 2010, and Microsoft Outlook 2013, clients should never pass the **MAPI_LOGOFF_SHARED** parameter to [IMAPISession::Logoff](imapisession-logoff.md).</span></span> <span data-ttu-id="ac6e5-140">传递**MAPI_LOGOFF_SHARED**都将导致开始关闭所有 MAPI 客户端和出现异常的行为，则会发生。</span><span class="sxs-lookup"><span data-stu-id="ac6e5-140">Passing **MAPI_LOGOFF_SHARED** will cause all MAPI clients to begin shutdown and unexpected behavior will occur.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ac6e5-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac6e5-141">See also</span></span>



[<span data-ttu-id="ac6e5-142">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ac6e5-142">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="ac6e5-143">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="ac6e5-143">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="ac6e5-144">结束 MAPI 会话</span><span class="sxs-lookup"><span data-stu-id="ac6e5-144">Ending a MAPI Session</span></span>](ending-a-mapi-session.md)

