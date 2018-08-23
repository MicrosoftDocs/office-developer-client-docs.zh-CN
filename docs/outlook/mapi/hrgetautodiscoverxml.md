---
title: HrGetAutoDiscoverXML
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- HrGetAutoDiscoverXML
api_type:
- COM
ms.assetid: 03691187-7c65-620b-576f-6ebe62a80830
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 490c834ee63c158b3f9c0e34f8de7f582c650bc4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584063"
---
# <a name="hrgetautodiscoverxml"></a><span data-ttu-id="b6388-103">HrGetAutoDiscoverXML</span><span class="sxs-lookup"><span data-stu-id="b6388-103">HrGetAutoDiscoverXML</span></span>

  
  
<span data-ttu-id="b6388-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b6388-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b6388-105">返回一个值，该值代表从 Microsoft Exchange 2007 服务器的自动发现服务检索信息的可扩展标记语言 (XML) 流。</span><span class="sxs-lookup"><span data-stu-id="b6388-105">Returns an Extensible Markup Language (XML) stream that represents information retrieved from the auto-discovery service of a Microsoft Exchange 2007 server.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="b6388-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="b6388-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b6388-107">导出：</span><span class="sxs-lookup"><span data-stu-id="b6388-107">Exported by:</span></span>  <br/> |<span data-ttu-id="b6388-108">olmapi32.dll</span><span class="sxs-lookup"><span data-stu-id="b6388-108">olmapi32.dll</span></span>  <br/> |
|<span data-ttu-id="b6388-109">调用：</span><span class="sxs-lookup"><span data-stu-id="b6388-109">Called by:</span></span>  <br/> |<span data-ttu-id="b6388-110">客户端</span><span class="sxs-lookup"><span data-stu-id="b6388-110">Client</span></span>  <br/> |
|<span data-ttu-id="b6388-111">通过实现：</span><span class="sxs-lookup"><span data-stu-id="b6388-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="b6388-112">Outlook</span><span class="sxs-lookup"><span data-stu-id="b6388-112">Outlook</span></span>  <br/> |
   
```cpp
HRESULT HrGetAutoDiscoverXML( 
    __in_z const WCHAR *pwzAddress, 
    __in_opt_z const WCHAR *pwzPassword, 
    __in_opt HANDLE hCancelEvent, 
    __in_opt ULONG ulFlags, 
    __out IStream** ppXmlStream); 

```

## <a name="parameters"></a><span data-ttu-id="b6388-113">参数</span><span class="sxs-lookup"><span data-stu-id="b6388-113">Parameters</span></span>

 <span data-ttu-id="b6388-114">_pwzAddress_</span><span class="sxs-lookup"><span data-stu-id="b6388-114">_pwzAddress_</span></span>
  
> <span data-ttu-id="b6388-115">[in]Null 结尾简单邮件传输协议 (SMTP) 电子邮件地址要检索的自动发现信息的帐户。</span><span class="sxs-lookup"><span data-stu-id="b6388-115">[in] A null-terminated Simple Mail Transfer Protocol (SMTP) email address of the account for which you want to retrieve the auto-discovery information.</span></span>
    
 <span data-ttu-id="b6388-116">_pwzPassword_</span><span class="sxs-lookup"><span data-stu-id="b6388-116">_pwzPassword_</span></span>
  
> <span data-ttu-id="b6388-117">[in]指定_pwzAddress_帐户可选密码。</span><span class="sxs-lookup"><span data-stu-id="b6388-117">[in] An optional password for the account specified by  _pwzAddress_.</span></span> <span data-ttu-id="b6388-118">请注意，是否_pwzAddress_指定的帐户不需要密码，传递任何密码没有任何效果。</span><span class="sxs-lookup"><span data-stu-id="b6388-118">Note that passing any password has no effect if the account specified by  _pwzAddress_ does not require a password.</span></span> 
    
 <span data-ttu-id="b6388-119">_hCancelEvent_</span><span class="sxs-lookup"><span data-stu-id="b6388-119">_hCancelEvent_</span></span>
  
> <span data-ttu-id="b6388-120">[in]未设置的 Win32 事件句柄的是可选的可使用以取消操作。</span><span class="sxs-lookup"><span data-stu-id="b6388-120">[in] An unset Win32 event handle that is optional and can be used to cancel the operation.</span></span> <span data-ttu-id="b6388-121">若要取消操作，设置事件，并为_hCancelEvent_; 传递事件句柄如果您不希望以取消操作，则传递**null** 。</span><span class="sxs-lookup"><span data-stu-id="b6388-121">To cancel the operation, set the event and pass the event handle as  _hCancelEvent_; pass **null** if you do not want to cancel the operation.</span></span> <span data-ttu-id="b6388-122">将值传递不代表事件句柄的注释不起作用，并忽略函数。</span><span class="sxs-lookup"><span data-stu-id="b6388-122">Note that passing a value that does not represent an event handle has no effect and is ignored by the function.</span></span> 
    
 <span data-ttu-id="b6388-123">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b6388-123">_ulFlags_</span></span>
  
> <span data-ttu-id="b6388-124">[in]不使用此参数。</span><span class="sxs-lookup"><span data-stu-id="b6388-124">[in] This parameter is not used.</span></span> <span data-ttu-id="b6388-125">它必须是 0。</span><span class="sxs-lookup"><span data-stu-id="b6388-125">It must be 0.</span></span>
    
 <span data-ttu-id="b6388-126">_ppXmlStream_</span><span class="sxs-lookup"><span data-stu-id="b6388-126">_ppXmlStream_</span></span>
  
> <span data-ttu-id="b6388-127">[输出]指向包含自动发现 XML 的[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b6388-127">[out] A pointer to an [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx) object that contains the autodiscovery XML.</span></span> <span data-ttu-id="b6388-128">如果自动发现操作失败，则返回**null** 。</span><span class="sxs-lookup"><span data-stu-id="b6388-128">Returns **null** if the autodiscovery operation fails.</span></span> <span data-ttu-id="b6388-129">在与之完成时，您必须释放[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)对象。</span><span class="sxs-lookup"><span data-stu-id="b6388-129">You must release the [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx) object when you are finished with it.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="b6388-130">返回值</span><span class="sxs-lookup"><span data-stu-id="b6388-130">Return values</span></span>

<span data-ttu-id="b6388-131">S_OK</span><span class="sxs-lookup"><span data-stu-id="b6388-131">S_OK</span></span> 
  
- <span data-ttu-id="b6388-132">成功函数调用。</span><span class="sxs-lookup"><span data-stu-id="b6388-132">The function call is successful.</span></span>
    
<span data-ttu-id="b6388-133">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b6388-133">E_INVALIDARG</span></span> 
  
-  <span data-ttu-id="b6388-134">_pwzAddress_为**null**或不是有效的 SMTP 地址，或_ppXmlStream_是**null**指向[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)对象。</span><span class="sxs-lookup"><span data-stu-id="b6388-134">_pwzAddress_ is **null** or is not a valid SMTP address, or  _ppXmlStream_ is a **null** pointer to an [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx) object.</span></span> 
    
<span data-ttu-id="b6388-135">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="b6388-135">MAPI_E_NOT_FOUND</span></span> 
  
- <span data-ttu-id="b6388-136">客户端计算机未连接到网络、 客户端计算机未连接到 Microsoft Exchange 2007 服务器、 _pwzAddress_不是在 Exchange 2007 服务器上，帐户或_pwzAddress_是不支持 Exchange 帐户自动发现服务。</span><span class="sxs-lookup"><span data-stu-id="b6388-136">Client computer is not connected to the network, client computer is not connected to a Microsoft Exchange 2007 server,  _pwzAddress_ is not an account on an Exchange 2007 server, or  _pwzAddress_ is an account that does not support Exchange auto-discovery service.</span></span> 
    
<span data-ttu-id="b6388-137">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="b6388-137">MAPI_E_USER_CANCEL</span></span> 
  
- <span data-ttu-id="b6388-138">事件句柄已传递到_hCancelEvent_以取消操作。</span><span class="sxs-lookup"><span data-stu-id="b6388-138">An event handle has been passed to  _hCancelEvent_ to cancel the operation.</span></span> 
    
<span data-ttu-id="b6388-139">STRSAFE_E_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="b6388-139">STRSAFE_E_INSUFFICIENT_BUFFER</span></span>
  
- <span data-ttu-id="b6388-140">传递给_pwzAddress_或_pwzPassword_值过长，以便它超出的内部缓冲区的大小 256 字节。</span><span class="sxs-lookup"><span data-stu-id="b6388-140">The value passed to  _pwzAddress_ or  _pwzPassword_ is too long, such that it overflows the internal buffer of size 256 bytes.</span></span> 
    

