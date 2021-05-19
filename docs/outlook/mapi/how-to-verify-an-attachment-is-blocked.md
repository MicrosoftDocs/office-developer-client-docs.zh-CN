---
title: 验证附件是否已遭阻止
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 69663470-45f3-86ed-e015-eba32b5a7233
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: c1c6f960f2e24108bebdc8f6cbf08bf1d94d85ae
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345883"
---
# <a name="verify-an-attachment-is-blocked"></a>验证附件是否已遭阻止

**适用于**：Outlook 2013 | Outlook 2016 
  
此 C++ 代码示例演示如何使用[IAttachmentSecurity ： IUnknown](iattachmentsecurityiunknown.md)接口来查明附件是否被 Microsoft Outlook 2010 或 Microsoft Outlook 2013 进行查看和索引。 
  
[IAttachmentSecurity ：IUnknown](iattachmentsecurityiunknown.md) 派生自 [IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx) 接口。 可以通过调用 MAPI 会话对象上的 [IUnknown：：QueryInterface，](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)请求获取 [IAttachmentSecurity ： IUnknown](iattachmentsecurityiunknown.md) IID_IAttachmentSecurity **。** 如果 Outlook 2010 或 Outlook 2013 认为附件不安全，并且阻止在 Outlook 2010 或 Outlook 2013 中查看和编制索引，[则 IAttachmentSecurity：：IsAttachmentBlocked](iattachmentsecurity-isattachmentblocked.md)在 _pfBlocked_ 中返回 **true。** 
  
```cpp
HRESULT IsAttachmentBlocked(LPMAPISESSION lpMAPISession, LPCWSTR pwszFileName, BOOL* pfBlocked) 
{ 
    if (!lpMAPISession || !pwszFileName || !pfBlocked) return MAPI_E_INVALID_PARAMETER; 
 
    HRESULT hRes = S_OK; 
    IAttachmentSecurity* lpAttachSec = NULL; 
    BOOL bBlocked = false; 
 
    hRes = lpMAPISession-&gt;QueryInterface(IID_IAttachmentSecurity,(void**)&amp;lpAttachSec); 
    if (SUCCEEDED(hRes) &amp;&amp; lpAttachSec) 
    { 
        hRes = lpAttachSec-&gt;IsAttachmentBlocked(pwszFileName,&amp;bBlocked); 
    } 
    if (lpAttachSec) lpAttachSec-&gt;Release(); 
 
    *pfBlocked = bBlocked; 
    return hRes; 
}

```


