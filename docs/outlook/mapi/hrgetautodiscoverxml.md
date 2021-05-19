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
ms.openlocfilehash: 77f28654ffe0f6f459fde229bb7428f2c39e96c0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32347801"
---
# <a name="hrgetautodiscoverxml"></a><span data-ttu-id="ad695-103">HrGetAutoDiscoverXML</span><span class="sxs-lookup"><span data-stu-id="ad695-103">HrGetAutoDiscoverXML</span></span>

  
  
<span data-ttu-id="ad695-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ad695-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ad695-105">返回 Extensible Markup Language (XML) stream，该流表示从 Microsoft Exchange 2007 服务器的自动发现服务检索的信息。</span><span class="sxs-lookup"><span data-stu-id="ad695-105">Returns an Extensible Markup Language (XML) stream that represents information retrieved from the auto-discovery service of a Microsoft Exchange 2007 server.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="ad695-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="ad695-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ad695-107">导出者：</span><span class="sxs-lookup"><span data-stu-id="ad695-107">Exported by:</span></span>  <br/> |<span data-ttu-id="ad695-108">olmapi32.dll</span><span class="sxs-lookup"><span data-stu-id="ad695-108">olmapi32.dll</span></span>  <br/> |
|<span data-ttu-id="ad695-109">调用者：</span><span class="sxs-lookup"><span data-stu-id="ad695-109">Called by:</span></span>  <br/> |<span data-ttu-id="ad695-110">客户端</span><span class="sxs-lookup"><span data-stu-id="ad695-110">Client</span></span>  <br/> |
|<span data-ttu-id="ad695-111">实现者：</span><span class="sxs-lookup"><span data-stu-id="ad695-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="ad695-112">Outlook</span><span class="sxs-lookup"><span data-stu-id="ad695-112">Outlook</span></span>  <br/> |
   
```cpp
HRESULT HrGetAutoDiscoverXML( 
    __in_z const WCHAR *pwzAddress, 
    __in_opt_z const WCHAR *pwzPassword, 
    __in_opt HANDLE hCancelEvent, 
    __in_opt ULONG ulFlags, 
    __out IStream** ppXmlStream); 

```

## <a name="parameters"></a><span data-ttu-id="ad695-113">参数</span><span class="sxs-lookup"><span data-stu-id="ad695-113">Parameters</span></span>

 <span data-ttu-id="ad695-114">_pwzAddress_</span><span class="sxs-lookup"><span data-stu-id="ad695-114">_pwzAddress_</span></span>
  
> <span data-ttu-id="ad695-115">[in]以 null 终止的简单邮件传输 (SMTP) 要检索其自动发现信息的帐户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="ad695-115">[in] A null-terminated Simple Mail Transfer Protocol (SMTP) email address of the account for which you want to retrieve the auto-discovery information.</span></span>
    
 <span data-ttu-id="ad695-116">_pwzPassword_</span><span class="sxs-lookup"><span data-stu-id="ad695-116">_pwzPassword_</span></span>
  
> <span data-ttu-id="ad695-117">[in]由  _pwzAddress 指定的_ 帐户的可选密码。</span><span class="sxs-lookup"><span data-stu-id="ad695-117">[in] An optional password for the account specified by  _pwzAddress_.</span></span> <span data-ttu-id="ad695-118">请注意，如果  _pwzAddress_ 指定的帐户不需要密码，则传递任何密码都无效。</span><span class="sxs-lookup"><span data-stu-id="ad695-118">Note that passing any password has no effect if the account specified by  _pwzAddress_ does not require a password.</span></span> 
    
 <span data-ttu-id="ad695-119">_hCancelEvent_</span><span class="sxs-lookup"><span data-stu-id="ad695-119">_hCancelEvent_</span></span>
  
> <span data-ttu-id="ad695-120">[in]可选的未设置 Win32 事件句柄，可用于取消操作。</span><span class="sxs-lookup"><span data-stu-id="ad695-120">[in] An unset Win32 event handle that is optional and can be used to cancel the operation.</span></span> <span data-ttu-id="ad695-121">若要取消操作，请设置 事件，将事件句柄传递为  _hCancelEvent_;如果 **不想** 取消操作，请传递 null。</span><span class="sxs-lookup"><span data-stu-id="ad695-121">To cancel the operation, set the event and pass the event handle as  _hCancelEvent_; pass **null** if you do not want to cancel the operation.</span></span> <span data-ttu-id="ad695-122">请注意，传递不代表事件句柄的值不起作用，函数将忽略该值。</span><span class="sxs-lookup"><span data-stu-id="ad695-122">Note that passing a value that does not represent an event handle has no effect and is ignored by the function.</span></span> 
    
 <span data-ttu-id="ad695-123">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ad695-123">_ulFlags_</span></span>
  
> <span data-ttu-id="ad695-124">[in]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="ad695-124">[in] This parameter is not used.</span></span> <span data-ttu-id="ad695-125">它必须是 0。</span><span class="sxs-lookup"><span data-stu-id="ad695-125">It must be 0.</span></span>
    
 <span data-ttu-id="ad695-126">_ppXmlStream_</span><span class="sxs-lookup"><span data-stu-id="ad695-126">_ppXmlStream_</span></span>
  
> <span data-ttu-id="ad695-127">[out]指向包含自动发现 XML 的 [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="ad695-127">[out] A pointer to an [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) object that contains the autodiscovery XML.</span></span> <span data-ttu-id="ad695-128">如果 **自动** 发现操作失败，则返回 null。</span><span class="sxs-lookup"><span data-stu-id="ad695-128">Returns **null** if the autodiscovery operation fails.</span></span> <span data-ttu-id="ad695-129">完成 [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 对象后，必须释放该对象。</span><span class="sxs-lookup"><span data-stu-id="ad695-129">You must release the [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) object when you are finished with it.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="ad695-130">返回值</span><span class="sxs-lookup"><span data-stu-id="ad695-130">Return values</span></span>

<span data-ttu-id="ad695-131">S_OK</span><span class="sxs-lookup"><span data-stu-id="ad695-131">S_OK</span></span> 
  
- <span data-ttu-id="ad695-132">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="ad695-132">The function call is successful.</span></span>
    
<span data-ttu-id="ad695-133">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ad695-133">E_INVALIDARG</span></span> 
  
-  <span data-ttu-id="ad695-134">_pwzAddress_ **为 null** 或不是有效的 SMTP 地址，或者 _ppXmlStream_ 是指向 [IStream 对象的](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)**空** 指针。</span><span class="sxs-lookup"><span data-stu-id="ad695-134">_pwzAddress_ is **null** or is not a valid SMTP address, or  _ppXmlStream_ is a **null** pointer to an [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) object.</span></span> 
    
<span data-ttu-id="ad695-135">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="ad695-135">MAPI_E_NOT_FOUND</span></span> 
  
- <span data-ttu-id="ad695-136">客户端计算机未连接到网络、客户端计算机未连接到 Microsoft Exchange 2007 服务器 _、pwzAddress_ 不是 Exchange 2007 服务器的帐户，或者 _pwzAddress_ 是不支持 Exchange 自动发现服务的帐户。</span><span class="sxs-lookup"><span data-stu-id="ad695-136">Client computer is not connected to the network, client computer is not connected to a Microsoft Exchange 2007 server,  _pwzAddress_ is not an account on an Exchange 2007 server, or  _pwzAddress_ is an account that does not support Exchange auto-discovery service.</span></span> 
    
<span data-ttu-id="ad695-137">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="ad695-137">MAPI_E_USER_CANCEL</span></span> 
  
- <span data-ttu-id="ad695-138">事件句柄已传递到  _hCancelEvent_ 以取消操作。</span><span class="sxs-lookup"><span data-stu-id="ad695-138">An event handle has been passed to  _hCancelEvent_ to cancel the operation.</span></span> 
    
<span data-ttu-id="ad695-139">STRSAFE_E_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="ad695-139">STRSAFE_E_INSUFFICIENT_BUFFER</span></span>
  
- <span data-ttu-id="ad695-140">传递给  _pwzAddress_ 或  _pwzPassword_ 的值太长，因此它会溢出大小为 256 字节的内部缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ad695-140">The value passed to  _pwzAddress_ or  _pwzPassword_ is too long, such that it overflows the internal buffer of size 256 bytes.</span></span> 
    

