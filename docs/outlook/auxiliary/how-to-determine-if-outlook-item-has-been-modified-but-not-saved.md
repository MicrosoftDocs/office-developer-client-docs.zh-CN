---
title: '确定项目Outlook是否已被修改，但没有保存到辅助 (Outlook引用) '
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 65fba557-5fb0-42de-8715-eccda1f3c648
description: 本主题演示如何使用dispidFDirty调度 ID 调用相应的属性，Outlook 项，可查看该项目是否已修改，并且尚未保存。
ms.openlocfilehash: 5dc20a45342e0434ab19d7c2347e98dec27b61b8
ms.sourcegitcommit: 007aa2ceb4f569201c3f4372de5c83b6c61f8875
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2020
ms.locfileid: "43102945"
---
# <a name="determine-if-an-outlook-item-has-been-modified-but-not-saved-outlook-auxiliary-reference"></a>确定项目Outlook是否已被修改，但没有保存到辅助 (Outlook引用) 

本主题演示如何使用 **dispidFDirty** 调度 ID 调用相应的属性，Outlook 项，可查看该项目是否已修改，并且尚未保存。 
  
给定一个 item 对象，可以使用[IUnknown::QueryInterface](https://docs.microsoft.com/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))方法来获取的[IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch)接口指针。 主题中的 函数 `FIsItemDirty` 接受 **IDispatch** 指针  _pdisp_ 作为输入参数。  `FIsItemDirty`调用 [IDispatch::Invoke](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke)方法，指定 **dispIdMember** 参数，该参数和 _wFlags_，标志 `DISPATCH_METHOD | DISPATCH_PROPERTYGET` _dispidFDirty_ 以验证该项目是否已修改。  `FIsItemDirty` 返回一个布尔 (**True** ，以指示该项目具有未保存的更改;否则为 **False**) 。
  
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

## <a name="see-also"></a>另请参阅

- [（Outlook 导出的 Api） 的常量](constants-outlook-exported-apis.md)

