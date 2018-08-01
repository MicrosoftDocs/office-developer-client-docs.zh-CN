---
title: IMAPISupportDoConfigPropsheet
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.DoConfigPropsheet
api_type:
- COM
ms.assetid: 3899c49c-a0ec-4dca-92e8-e801cd4908cf
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 06341f897a7865c09a565db67bb409fc9f49f8da
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775613"
---
# <a name="imapisupportdoconfigpropsheet"></a><span data-ttu-id="31a70-103">IMAPISupport::DoConfigPropsheet</span><span class="sxs-lookup"><span data-stu-id="31a70-103">IMAPISupport::DoConfigPropsheet</span></span>

  
  
<span data-ttu-id="31a70-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="31a70-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="31a70-105">显示配置属性表。</span><span class="sxs-lookup"><span data-stu-id="31a70-105">Displays a configuration property sheet.</span></span>
  
```cpp
HRESULT DoConfigPropsheet(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPSTR lpszTitle,
  LPMAPITABLE lpDisplayTable,
  LPMAPIPROP lpConfigData,
  ULONG ulTopPage
);
```

## <a name="parameters"></a><span data-ttu-id="31a70-106">参数</span><span class="sxs-lookup"><span data-stu-id="31a70-106">Parameters</span></span>

 <span data-ttu-id="31a70-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="31a70-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="31a70-108">[in]属性表的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="31a70-108">[in] A handle to the parent window of the property sheet.</span></span>
    
 <span data-ttu-id="31a70-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="31a70-109">_ulFlags_</span></span>
  
> <span data-ttu-id="31a70-110">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="31a70-110">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="31a70-111">_lpszTitle_</span><span class="sxs-lookup"><span data-stu-id="31a70-111">_lpszTitle_</span></span>
  
> <span data-ttu-id="31a70-112">[in]一个指向属性表的标题。</span><span class="sxs-lookup"><span data-stu-id="31a70-112">[in] A pointer to the title of the property sheet.</span></span>
    
 <span data-ttu-id="31a70-113">_lpDisplayTable_</span><span class="sxs-lookup"><span data-stu-id="31a70-113">_lpDisplayTable_</span></span>
  
> <span data-ttu-id="31a70-114">[in]指向显示表在属性表中描述的控件显示的指针。</span><span class="sxs-lookup"><span data-stu-id="31a70-114">[in] A pointer to the display table that describes the controls to appear on the property sheet.</span></span>
    
 <span data-ttu-id="31a70-115">_lpConfigData_</span><span class="sxs-lookup"><span data-stu-id="31a70-115">_lpConfigData_</span></span>
  
> <span data-ttu-id="31a70-116">[in]指向要用于访问的配置属性用于在属性表中显示的[IMAPIProp](imapipropiunknown.md)实现的指针。</span><span class="sxs-lookup"><span data-stu-id="31a70-116">[in] A pointer to the [IMAPIProp](imapipropiunknown.md) implementation to be used for accessing the configuration properties to be displayed on the property sheet.</span></span> 
    
 <span data-ttu-id="31a70-117">_ulTopPage_</span><span class="sxs-lookup"><span data-stu-id="31a70-117">_ulTopPage_</span></span>
  
> <span data-ttu-id="31a70-118">[in]属性表的默认顶级网页到一个从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="31a70-118">[in] A zero-based index to the default top page of the property sheet.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="31a70-119">返回值</span><span class="sxs-lookup"><span data-stu-id="31a70-119">Return value</span></span>

<span data-ttu-id="31a70-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="31a70-120">S_OK</span></span> 
  
> <span data-ttu-id="31a70-121">显示已配置的属性表。</span><span class="sxs-lookup"><span data-stu-id="31a70-121">The configuration property sheet was displayed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="31a70-122">说明</span><span class="sxs-lookup"><span data-stu-id="31a70-122">Remarks</span></span>

<span data-ttu-id="31a70-123">对于所有支持对象实现**IMAPISupport::DoConfigPropsheet**方法。</span><span class="sxs-lookup"><span data-stu-id="31a70-123">The **IMAPISupport::DoConfigPropsheet** method is implemented for all support objects.</span></span> <span data-ttu-id="31a70-124">**DoConfigPropSheet**提供标准用户界面，用于显示服务提供商和消息服务的属性。</span><span class="sxs-lookup"><span data-stu-id="31a70-124">**DoConfigPropSheet** provides a standard user interface for displaying the properties of service providers and message services.</span></span> <span data-ttu-id="31a70-125">使用户受益于一致的 Windows 接口，应用于所有配置属性显示此标准的对话框。</span><span class="sxs-lookup"><span data-stu-id="31a70-125">You should use this standard dialog box for all configuration property displays so that users benefit from a consistent Windows interface.</span></span> 
  
<span data-ttu-id="31a70-126">服务提供商调用**DoConfigPropSheet**作为其实现[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)方法时，或者从用来显示属性的详细信息的按钮的一部分。</span><span class="sxs-lookup"><span data-stu-id="31a70-126">Service providers call **DoConfigPropSheet** as part of their implementation of the [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) method or from a button used to display details on properties.</span></span> <span data-ttu-id="31a70-127">消息服务从其消息服务入口点函数调用**DoConfigPropSheet** 。</span><span class="sxs-lookup"><span data-stu-id="31a70-127">Message services call **DoConfigPropSheet** from their message service entry point function.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="31a70-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="31a70-128">Notes to callers</span></span>

<span data-ttu-id="31a70-129">您可以创建通过调用[BuildDisplayTable](builddisplaytable.md)函数或自定义代码_lpDisplayTable_参数指向显示表。</span><span class="sxs-lookup"><span data-stu-id="31a70-129">You can create the display table pointed to by the  _lpDisplayTable_ parameter by calling the [BuildDisplayTable](builddisplaytable.md) function or with custom code.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="31a70-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31a70-130">See also</span></span>



[<span data-ttu-id="31a70-131">BuildDisplayTable</span><span class="sxs-lookup"><span data-stu-id="31a70-131">BuildDisplayTable</span></span>](builddisplaytable.md)
  
[<span data-ttu-id="31a70-132">CreateIProp</span><span class="sxs-lookup"><span data-stu-id="31a70-132">CreateIProp</span></span>](createiprop.md)
  
[<span data-ttu-id="31a70-133">IABProvider::Logon</span><span class="sxs-lookup"><span data-stu-id="31a70-133">IABProvider::Logon</span></span>](iabprovider-logon.md)
  
[<span data-ttu-id="31a70-134">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="31a70-134">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)
  
[<span data-ttu-id="31a70-135">IMAPIStatus::SettingsDialog</span><span class="sxs-lookup"><span data-stu-id="31a70-135">IMAPIStatus::SettingsDialog</span></span>](imapistatus-settingsdialog.md)
  
[<span data-ttu-id="31a70-136">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="31a70-136">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)
  
[<span data-ttu-id="31a70-137">IMSProvider::Logon</span><span class="sxs-lookup"><span data-stu-id="31a70-137">IMSProvider::Logon</span></span>](imsprovider-logon.md)
  
[<span data-ttu-id="31a70-138">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="31a70-138">IXPProvider::TransportLogon</span></span>](ixpprovider-transportlogon.md)
  
[<span data-ttu-id="31a70-139">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="31a70-139">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

