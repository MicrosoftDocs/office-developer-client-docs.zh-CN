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
  
此代码示例在 c + + 中显示了如何使用[IAttachmentSecurity: IUnknown](iattachmentsecurityiunknown.md)接口来确定 microsoft outlook 2010 或 microsoft outlook 2013 是否阻止了附件查看和编制索引。 
  
[IAttachmentSecurity: iunknown](iattachmentsecurityiunknown.md)是从[iunknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx)接口派生的。 您可以通过调用[iunknown:: QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)在 MAPI session 对象上获取[IAttachmentSecurity: IUnknown](iattachmentsecurityiunknown.md)接口, 请求**IID_IAttachmentSecurity**。 [IAttachmentSecurity:: IsAttachmentBlocked](iattachmentsecurity-isattachmentblocked.md)如果附件被 outlook 2010 或 outlook 2013 认为是不安全的, 并且被阻止在 outlook 2010 或 outlook 2013 中查看和编制索引, 则在_pfBlocked_中将返回**true** 。 
  
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


