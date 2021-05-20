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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: cd8727104af694d456074614b5ea7c222c9b91b9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429011"
---
# <a name="imapisupportdoconfigpropsheet"></a><span data-ttu-id="9c812-103">IMAPISupport::DoConfigPropsheet</span><span class="sxs-lookup"><span data-stu-id="9c812-103">IMAPISupport::DoConfigPropsheet</span></span>

  
  
<span data-ttu-id="9c812-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9c812-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9c812-105">显示配置属性表。</span><span class="sxs-lookup"><span data-stu-id="9c812-105">Displays a configuration property sheet.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="9c812-106">参数</span><span class="sxs-lookup"><span data-stu-id="9c812-106">Parameters</span></span>

 <span data-ttu-id="9c812-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="9c812-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="9c812-108">[in]父窗口的句柄属性表。</span><span class="sxs-lookup"><span data-stu-id="9c812-108">[in] A handle to the parent window of the property sheet.</span></span>
    
 <span data-ttu-id="9c812-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="9c812-109">_ulFlags_</span></span>
  
> <span data-ttu-id="9c812-110">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="9c812-110">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="9c812-111">_lpszTitle_</span><span class="sxs-lookup"><span data-stu-id="9c812-111">_lpszTitle_</span></span>
  
> <span data-ttu-id="9c812-112">[in]指向项目标题的属性表。</span><span class="sxs-lookup"><span data-stu-id="9c812-112">[in] A pointer to the title of the property sheet.</span></span>
    
 <span data-ttu-id="9c812-113">_lpDisplayTable_</span><span class="sxs-lookup"><span data-stu-id="9c812-113">_lpDisplayTable_</span></span>
  
> <span data-ttu-id="9c812-114">[in]指向显示表的指针，该显示表描述要显示在属性表。</span><span class="sxs-lookup"><span data-stu-id="9c812-114">[in] A pointer to the display table that describes the controls to appear on the property sheet.</span></span>
    
 <span data-ttu-id="9c812-115">_lpConfigData_</span><span class="sxs-lookup"><span data-stu-id="9c812-115">_lpConfigData_</span></span>
  
> <span data-ttu-id="9c812-116">[in]指向 [IMAPIProp](imapipropiunknown.md) 实现（用于访问要显示在 属性表 上的配置属性）的指针。</span><span class="sxs-lookup"><span data-stu-id="9c812-116">[in] A pointer to the [IMAPIProp](imapipropiunknown.md) implementation to be used for accessing the configuration properties to be displayed on the property sheet.</span></span> 
    
 <span data-ttu-id="9c812-117">_ulTopPage_</span><span class="sxs-lookup"><span data-stu-id="9c812-117">_ulTopPage_</span></span>
  
> <span data-ttu-id="9c812-118">[in]从零开始到默认页面的索引属性表。</span><span class="sxs-lookup"><span data-stu-id="9c812-118">[in] A zero-based index to the default top page of the property sheet.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9c812-119">返回值</span><span class="sxs-lookup"><span data-stu-id="9c812-119">Return value</span></span>

<span data-ttu-id="9c812-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="9c812-120">S_OK</span></span> 
  
> <span data-ttu-id="9c812-121">配置属性表显示。</span><span class="sxs-lookup"><span data-stu-id="9c812-121">The configuration property sheet was displayed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9c812-122">备注</span><span class="sxs-lookup"><span data-stu-id="9c812-122">Remarks</span></span>

<span data-ttu-id="9c812-123">**IMAPISupport：:D oConfigPropsheet** 方法针对所有支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="9c812-123">The **IMAPISupport::DoConfigPropsheet** method is implemented for all support objects.</span></span> <span data-ttu-id="9c812-124">**DoConfigPropSheet** 提供了用于显示服务提供程序和邮件服务的属性的标准用户界面。</span><span class="sxs-lookup"><span data-stu-id="9c812-124">**DoConfigPropSheet** provides a standard user interface for displaying the properties of service providers and message services.</span></span> <span data-ttu-id="9c812-125">应针对所有配置属性显示使用此标准对话框，以便用户受益于一致的Windows界面。</span><span class="sxs-lookup"><span data-stu-id="9c812-125">You should use this standard dialog box for all configuration property displays so that users benefit from a consistent Windows interface.</span></span> 
  
<span data-ttu-id="9c812-126">服务提供商在 [IMAPIStatus：：SettingsDialog](imapistatus-settingsdialog.md)方法的实现过程中，或者从用于显示属性详细信息的按钮调用 **DoConfigPropSheet。**</span><span class="sxs-lookup"><span data-stu-id="9c812-126">Service providers call **DoConfigPropSheet** as part of their implementation of the [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) method or from a button used to display details on properties.</span></span> <span data-ttu-id="9c812-127">邮件服务从 **邮件服务入口点函数调用 DoConfigPropSheet。**</span><span class="sxs-lookup"><span data-stu-id="9c812-127">Message services call **DoConfigPropSheet** from their message service entry point function.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="9c812-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="9c812-128">Notes to callers</span></span>

<span data-ttu-id="9c812-129">您可以通过调用 [BuildDisplayTable](builddisplaytable.md)函数或自定义代码创建 _lpDisplayTable_ 参数指向的显示表。</span><span class="sxs-lookup"><span data-stu-id="9c812-129">You can create the display table pointed to by the  _lpDisplayTable_ parameter by calling the [BuildDisplayTable](builddisplaytable.md) function or with custom code.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9c812-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c812-130">See also</span></span>



[<span data-ttu-id="9c812-131">BuildDisplayTable</span><span class="sxs-lookup"><span data-stu-id="9c812-131">BuildDisplayTable</span></span>](builddisplaytable.md)
  
[<span data-ttu-id="9c812-132">CreateIProp</span><span class="sxs-lookup"><span data-stu-id="9c812-132">CreateIProp</span></span>](createiprop.md)
  
[<span data-ttu-id="9c812-133">IABProvider::Logon</span><span class="sxs-lookup"><span data-stu-id="9c812-133">IABProvider::Logon</span></span>](iabprovider-logon.md)
  
[<span data-ttu-id="9c812-134">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9c812-134">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)
  
[<span data-ttu-id="9c812-135">IMAPIStatus::SettingsDialog</span><span class="sxs-lookup"><span data-stu-id="9c812-135">IMAPIStatus::SettingsDialog</span></span>](imapistatus-settingsdialog.md)
  
[<span data-ttu-id="9c812-136">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9c812-136">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)
  
[<span data-ttu-id="9c812-137">IMSProvider::Logon</span><span class="sxs-lookup"><span data-stu-id="9c812-137">IMSProvider::Logon</span></span>](imsprovider-logon.md)
  
[<span data-ttu-id="9c812-138">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="9c812-138">IXPProvider::TransportLogon</span></span>](ixpprovider-transportlogon.md)
  
[<span data-ttu-id="9c812-139">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9c812-139">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

