---
title: 验证被阻止的附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 69663470-45f3-86ed-e015-eba32b5a7233
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: a21383e0ea6920075a57d872e82851462bf0e8d3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775129"
---
# <a name="verify-an-attachment-is-blocked"></a><span data-ttu-id="acc2e-103">验证被阻止的附件</span><span class="sxs-lookup"><span data-stu-id="acc2e-103">Verify an attachment is blocked</span></span>

<span data-ttu-id="acc2e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="acc2e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="acc2e-105">在 c + + 此代码示例演示如何使用[IAttachmentSecurity: IUnknown](iattachmentsecurityiunknown.md)接口以找出是否附件被阻止通过 Microsoft Outlook 2010 或 Microsoft Outlook 2013 的查看和编制索引。</span><span class="sxs-lookup"><span data-stu-id="acc2e-105">This code sample in C++ shows how to use the [IAttachmentSecurity : IUnknown](iattachmentsecurityiunknown.md) interface to find out whether an attachment is blocked by Microsoft Outlook 2010 or Microsoft Outlook 2013 for viewing and indexing.</span></span> 
  
<span data-ttu-id="acc2e-106">[IAttachmentSecurity: IUnknown](iattachmentsecurityiunknown.md)从[IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28VS.85%29.aspx)接口派生。</span><span class="sxs-lookup"><span data-stu-id="acc2e-106">[IAttachmentSecurity : IUnknown](iattachmentsecurityiunknown.md) is derived from the [IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28VS.85%29.aspx) interface.</span></span> <span data-ttu-id="acc2e-107">您可以获取[IAttachmentSecurity: IUnknown](iattachmentsecurityiunknown.md)通过 MAPI 会话对象，请求**IID_IAttachmentSecurity**调用[IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx)的接口。</span><span class="sxs-lookup"><span data-stu-id="acc2e-107">You can obtain the [IAttachmentSecurity : IUnknown](iattachmentsecurityiunknown.md) interface by calling [IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx) on the MAPI session object, requesting **IID_IAttachmentSecurity**.</span></span> <span data-ttu-id="acc2e-108">[IAttachmentSecurity::IsAttachmentBlocked](iattachmentsecurity-isattachmentblocked.md)返回**true**中_pfBlocked_如果附件通过 Outlook 2010 或 Outlook 2013 中被视为不安全和被阻止的查看和 Outlook 2010 或 Outlook 2013 中的索引。</span><span class="sxs-lookup"><span data-stu-id="acc2e-108">[IAttachmentSecurity::IsAttachmentBlocked](iattachmentsecurity-isattachmentblocked.md) returns **true** in  _pfBlocked_ if the attachment is considered unsafe by Outlook 2010 or Outlook 2013 and is blocked for viewing and indexing in Outlook 2010 or Outlook 2013.</span></span> 
  
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


