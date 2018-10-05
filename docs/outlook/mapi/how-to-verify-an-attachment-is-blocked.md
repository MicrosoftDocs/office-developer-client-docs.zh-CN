---
title: 验证被阻止的附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 69663470-45f3-86ed-e015-eba32b5a7233
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: c1c6f960f2e24108bebdc8f6cbf08bf1d94d85ae
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393836"
---
# <a name="verify-an-attachment-is-blocked"></a>验证被阻止的附件

**适用于**：Outlook 2013 | Outlook 2016 
  
在 c + + 此代码示例演示如何使用[IAttachmentSecurity: IUnknown](iattachmentsecurityiunknown.md)接口以找出是否附件被阻止通过 Microsoft Outlook 2010 或 Microsoft Outlook 2013 的查看和编制索引。 
  
[IAttachmentSecurity: IUnknown](iattachmentsecurityiunknown.md)从[IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx)接口派生。 您可以获取[IAttachmentSecurity: IUnknown](iattachmentsecurityiunknown.md)通过 MAPI 会话对象，请求**IID_IAttachmentSecurity**调用[IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)的接口。 [IAttachmentSecurity::IsAttachmentBlocked](iattachmentsecurity-isattachmentblocked.md)返回**true**中_pfBlocked_如果附件通过 Outlook 2010 或 Outlook 2013 中被视为不安全和被阻止的查看和 Outlook 2010 或 Outlook 2013 中的索引。 
  
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


