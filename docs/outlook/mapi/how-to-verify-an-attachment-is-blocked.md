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
# <a name="verify-an-attachment-is-blocked"></a><span data-ttu-id="8bf49-103">验证附件是否已遭阻止</span><span class="sxs-lookup"><span data-stu-id="8bf49-103">Verify an attachment is blocked</span></span>

<span data-ttu-id="8bf49-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8bf49-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8bf49-105">此 C++ 代码示例演示如何使用[IAttachmentSecurity ： IUnknown](iattachmentsecurityiunknown.md)接口来查明附件是否被 Microsoft Outlook 2010 或 Microsoft Outlook 2013 进行查看和索引。</span><span class="sxs-lookup"><span data-stu-id="8bf49-105">This code sample in C++ shows how to use the [IAttachmentSecurity : IUnknown](iattachmentsecurityiunknown.md) interface to find out whether an attachment is blocked by Microsoft Outlook 2010 or Microsoft Outlook 2013 for viewing and indexing.</span></span> 
  
<span data-ttu-id="8bf49-106">[IAttachmentSecurity ：IUnknown](iattachmentsecurityiunknown.md) 派生自 [IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx) 接口。</span><span class="sxs-lookup"><span data-stu-id="8bf49-106">[IAttachmentSecurity : IUnknown](iattachmentsecurityiunknown.md) is derived from the [IUnknown](https://msdn.microsoft.com/library/ms680509%28VS.85%29.aspx) interface.</span></span> <span data-ttu-id="8bf49-107">可以通过调用 MAPI 会话对象上的 [IUnknown：：QueryInterface，](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)请求获取 [IAttachmentSecurity ： IUnknown](iattachmentsecurityiunknown.md) IID_IAttachmentSecurity **。**</span><span class="sxs-lookup"><span data-stu-id="8bf49-107">You can obtain the [IAttachmentSecurity : IUnknown](iattachmentsecurityiunknown.md) interface by calling [IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) on the MAPI session object, requesting **IID_IAttachmentSecurity**.</span></span> <span data-ttu-id="8bf49-108">如果 Outlook 2010 或 Outlook 2013 认为附件不安全，并且阻止在 Outlook 2010 或 Outlook 2013 中查看和编制索引，[则 IAttachmentSecurity：：IsAttachmentBlocked](iattachmentsecurity-isattachmentblocked.md)在 _pfBlocked_ 中返回 **true。**</span><span class="sxs-lookup"><span data-stu-id="8bf49-108">[IAttachmentSecurity::IsAttachmentBlocked](iattachmentsecurity-isattachmentblocked.md) returns **true** in  _pfBlocked_ if the attachment is considered unsafe by Outlook 2010 or Outlook 2013 and is blocked for viewing and indexing in Outlook 2010 or Outlook 2013.</span></span> 
  
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


