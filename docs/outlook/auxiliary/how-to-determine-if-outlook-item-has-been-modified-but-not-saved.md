---
title: 确定 outlook 项目是否已修改但未保存 (outlook 辅助参考)
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 65fba557-5fb0-42de-8715-eccda1f3c648
description: 本主题演示如何使用dispidFDirty调度 ID 调用相应的属性，Outlook 项，可查看该项目是否已修改，并且尚未保存。
ms.openlocfilehash: e66a23983a3cc19a7cb51d4b4c3b2c1cee58a793
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317638"
---
# <a name="determine-if-an-outlook-item-has-been-modified-but-not-saved-outlook-auxiliary-reference"></a><span data-ttu-id="cd609-103">确定 outlook 项目是否已修改但未保存 (outlook 辅助参考)</span><span class="sxs-lookup"><span data-stu-id="cd609-103">Determine if an Outlook item has been modified but not saved (Outlook Auxiliary Reference)</span></span>

<span data-ttu-id="cd609-104">本主题演示如何使用 **dispidFDirty**调度 ID 调用相应的属性，Outlook 项，可查看该项目是否已修改，并且尚未保存。</span><span class="sxs-lookup"><span data-stu-id="cd609-104">This topic shows how to use the **dispidFDirty** dispatch ID to invoke the corresponding property on an Outlook item, to see whether the item has been modified and has not been saved.</span></span> 
  
<span data-ttu-id="cd609-105">给定一个 item 对象，可以使用[IUnknown::QueryInterface](https://docs.microsoft.com/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))方法来获取的[IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch)接口指针。</span><span class="sxs-lookup"><span data-stu-id="cd609-105">Given an item object, you can use the [IUnknown::QueryInterface](https://docs.microsoft.com/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) method to obtain an [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) interface pointer.</span></span> <span data-ttu-id="cd609-106">主题`FIsItemDirty`中的函数接受作为输入参数的**IDispatch**指针_pdisp_。</span><span class="sxs-lookup"><span data-stu-id="cd609-106">The function in the topic `FIsItemDirty` accepts an **IDispatch** pointer,  _pdisp_, as an input parameter.</span></span>  <span data-ttu-id="cd609-107">`FIsItemDirty`调用[IDispatch::Invoke](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke)方法，指定 **dispIdMember**参数，该参数和 _wFlags_，标志 `DISPATCH_METHOD | DISPATCH_PROPERTYGET` _dispidFDirty_以验证该项目是否已修改。</span><span class="sxs-lookup"><span data-stu-id="cd609-107">`FIsItemDirty` calls the [IDispatch::Invoke](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) method, specifying **dispidFDirty** as the argument for the  _dispIdMember_ parameter, and the flags  `DISPATCH_METHOD | DISPATCH_PROPERTYGET` for  _wFlags_, to verify whether the item has been modified.</span></span>  <span data-ttu-id="cd609-108">`FIsItemDirty`返回一个布尔值 (**True**表示项目具有未保存的更改; 否则为**False**)。</span><span class="sxs-lookup"><span data-stu-id="cd609-108">`FIsItemDirty` returns a Boolean value (**True** to indicate that the item has unsaved changes; otherwise, **False**).</span></span>
  
```cpp
bool FIsItemDirty(IDispatch *pdisp)
{
    DISPPARAMS dispparams;
    UINT uArgErr;
    HRESULT hr = S_OK;
    CComVariant varDirty;
    dispparams.rgvarg = 0;
    dispparams.cArgs = 0;
    dispparams.cNamedArgs = 0;
    dispparams.rgdispidNamedArgs = NULL;
    hr = pdisp->Invoke(dispidFDirty,
        IID_NULL,
        LOCALE_SYSTEM_DEFAULT,
        DISPATCH_METHOD | DISPATCH_PROPERTYGET,
        &amp;dispparams,
        &amp;varDirty,
        NULL,
        &amp;uArgErr);
    return SUCCEEDED(hr) &amp;&amp; varDirty.bVal;
}

```

## <a name="see-also"></a><span data-ttu-id="cd609-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd609-109">See also</span></span>

- [<span data-ttu-id="cd609-110">（Outlook 导出的 Api） 的常量</span><span class="sxs-lookup"><span data-stu-id="cd609-110">Constants (Outlook exported APIs)</span></span>](constants-outlook-exported-apis.md)

