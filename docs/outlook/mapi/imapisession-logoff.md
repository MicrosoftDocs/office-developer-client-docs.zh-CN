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
# <a name="imapisessionlogoff"></a><span data-ttu-id="e9b4c-103">IMAPISession::Logoff</span><span class="sxs-lookup"><span data-stu-id="e9b4c-103">IMAPISession::Logoff</span></span>

  
  
<span data-ttu-id="e9b4c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e9b4c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e9b4c-105">结束 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-105">Ends a MAPI session.</span></span>
  
```cpp
HRESULT Logoff(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  ULONG ulReserved
);
```

## <a name="parameters"></a><span data-ttu-id="e9b4c-106">参数</span><span class="sxs-lookup"><span data-stu-id="e9b4c-106">Parameters</span></span>

 <span data-ttu-id="e9b4c-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="e9b4c-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="e9b4c-108">实时要显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-108">[in] A handle to the parent window of any dialog boxes or windows to be displayed.</span></span> <span data-ttu-id="e9b4c-109">如果未设置 MAPI_LOGOFF_UI 标志, 则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-109">This parameter is ignored if the MAPI_LOGOFF_UI flag is not set.</span></span>
    
 <span data-ttu-id="e9b4c-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="e9b4c-110">_ulFlags_</span></span>
  
> <span data-ttu-id="e9b4c-111">实时控制注销操作的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-111">[in] A bitmask of flags that control the logoff operation.</span></span> <span data-ttu-id="e9b4c-112">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="e9b4c-112">The following flags can be set:</span></span>
    
<span data-ttu-id="e9b4c-113">MAPI_LOGOFF_SHARED</span><span class="sxs-lookup"><span data-stu-id="e9b4c-113">MAPI_LOGOFF_SHARED</span></span> 
  
> <span data-ttu-id="e9b4c-114">如果此会话是共享的, 则应通知使用共享会话登录的所有客户端正在进行的注销。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-114">If this session is shared, all clients that logged on by using the shared session should be notified of the logoff in progress.</span></span> <span data-ttu-id="e9b4c-115">客户端应注销。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-115">The clients should log off.</span></span> <span data-ttu-id="e9b4c-116">任何使用共享会话的客户端都可以设置此标志。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-116">Any client that is using the shared session can set this flag.</span></span> <span data-ttu-id="e9b4c-117">如果当前会话不是共享的, 则忽略 MAPI_LOGOFF_SHARED。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-117">MAPI_LOGOFF_SHARED is ignored if the current session is not shared.</span></span>
    
<span data-ttu-id="e9b4c-118">MAPI_LOGOFF_UI</span><span class="sxs-lookup"><span data-stu-id="e9b4c-118">MAPI_LOGOFF_UI</span></span> 
  
> <span data-ttu-id="e9b4c-119">**注销**可以在操作过程中显示对话框, 可能会提示用户进行确认。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-119">**Logoff** can display a dialog box during the operation, possibly prompting the user for confirmation.</span></span> 
    
 <span data-ttu-id="e9b4c-120">_ulReserved_</span><span class="sxs-lookup"><span data-stu-id="e9b4c-120">_ulReserved_</span></span>
  
> <span data-ttu-id="e9b4c-121">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-121">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e9b4c-122">返回值</span><span class="sxs-lookup"><span data-stu-id="e9b4c-122">Return value</span></span>

<span data-ttu-id="e9b4c-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="e9b4c-123">S_OK</span></span> 
  
> <span data-ttu-id="e9b4c-124">注销操作成功。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-124">The logoff operation was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e9b4c-125">注解</span><span class="sxs-lookup"><span data-stu-id="e9b4c-125">Remarks</span></span>

<span data-ttu-id="e9b4c-126">**IMAPISession:: 注销**方法结束 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-126">The **IMAPISession::Logoff** method ends a MAPI session.</span></span> <span data-ttu-id="e9b4c-127">当**注销**时, 将不会调用除了[IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)之外的任何方法。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-127">When **Logoff** returns, none of the methods except for [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) can be called.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="e9b4c-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="e9b4c-128">Notes to callers</span></span>

<span data-ttu-id="e9b4c-129">当**注销**时, 请通过调用其**IUnknown:: release**方法来释放 session 对象。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-129">When **Logoff** returns, release the session object by calling its **IUnknown::Release** method.</span></span> 
  
<span data-ttu-id="e9b4c-130">有关结束会话的详细信息, 请参阅[结束 MAPI 会话](ending-a-mapi-session.md)。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-130">For more information about ending a session, see [Ending a MAPI Session](ending-a-mapi-session.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="e9b4c-131">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="e9b4c-131">MFCMAPI reference</span></span>

<span data-ttu-id="e9b4c-132">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-132">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="e9b4c-133">**文件**</span><span class="sxs-lookup"><span data-stu-id="e9b4c-133">**File**</span></span>|<span data-ttu-id="e9b4c-134">**函数**</span><span class="sxs-lookup"><span data-stu-id="e9b4c-134">**Function**</span></span>|<span data-ttu-id="e9b4c-135">**备注**</span><span class="sxs-lookup"><span data-stu-id="e9b4c-135">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e9b4c-136">MAPIObjects</span><span class="sxs-lookup"><span data-stu-id="e9b4c-136">MAPIObjects.cpp</span></span>  <br/> |<span data-ttu-id="e9b4c-137">CMapiObjects:: 注销</span><span class="sxs-lookup"><span data-stu-id="e9b4c-137">CMapiObjects::Logoff</span></span>  <br/> |<span data-ttu-id="e9b4c-138">MFCMAPI 使用**IMAPISession:: 注销**方法从会话中注销, 然后再将其发布。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-138">MFCMAPI uses the **IMAPISession::Logoff** method to log off from the session before releasing it.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="e9b4c-139">由于 microsoft Office Outlook 2007 Service Pack 2、microsoft outlook 2010 和 microsoft outlook 2013 中引入了快速关闭行为, 客户端决不应将**MAPI_LOGOFF_SHARED**参数传递给[IMAPISession:: 注销](imapisession-logoff.md)。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-139">Due to the fast shutdown behavior introduced in Microsoft Office Outlook 2007 Service Pack 2, Microsoft Outlook 2010, and Microsoft Outlook 2013, clients should never pass the **MAPI_LOGOFF_SHARED** parameter to [IMAPISession::Logoff](imapisession-logoff.md).</span></span> <span data-ttu-id="e9b4c-140">传递**MAPI_LOGOFF_SHARED**将导致所有 MAPI 客户端都开始关闭, 并将发生意外行为。</span><span class="sxs-lookup"><span data-stu-id="e9b4c-140">Passing **MAPI_LOGOFF_SHARED** will cause all MAPI clients to begin shutdown and unexpected behavior will occur.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e9b4c-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9b4c-141">See also</span></span>



[<span data-ttu-id="e9b4c-142">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e9b4c-142">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="e9b4c-143">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="e9b4c-143">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="e9b4c-144">结束 MAPI 会话</span><span class="sxs-lookup"><span data-stu-id="e9b4c-144">Ending a MAPI Session</span></span>](ending-a-mapi-session.md)

