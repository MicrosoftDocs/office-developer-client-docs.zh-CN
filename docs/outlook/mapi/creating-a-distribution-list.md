---
title: 创建通讯组列表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b63a6024-910d-4569-a3b4-c3ebf0b32c3d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 82fa28f021dbb839c7bb05974682f0bb24174bb2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774721"
---
# <a name="creating-a-distribution-list"></a><span data-ttu-id="3bbf3-103">创建通讯组列表</span><span class="sxs-lookup"><span data-stu-id="3bbf3-103">Creating a distribution list</span></span>

<span data-ttu-id="3bbf3-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3bbf3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3bbf3-105">客户端可以直接在如个人通讯簿 (PAB) 可修改容器中创建通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-105">Clients can create a distribution list directly into a modifiable container such as the personal address book (PAB).</span></span>
  
<span data-ttu-id="3bbf3-106">**在 PAB 中创建通讯组列表**</span><span class="sxs-lookup"><span data-stu-id="3bbf3-106">**To create a distribution list in the PAB**</span></span>
  
1. <span data-ttu-id="3bbf3-107">使用一个属性标记， **PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md))，创建调整的属性标记数组，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3bbf3-107">Create a sized property tag array with one property tag, **PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md)), as follows:</span></span>
    
   ```cpp
    SizedPropTagArray(1, tagaDefaultDL) =
    {
        1,
        {
            PR_DEF_CREATE_DL
        }
    };
   ```

2. <span data-ttu-id="3bbf3-108">调用[IAddrBook::GetPAB](iaddrbook-getpab.md)检索 PAB 的项标识符。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-108">Call [IAddrBook::GetPAB](iaddrbook-getpab.md) to retrieve the entry identifier of the PAB.</span></span> <span data-ttu-id="3bbf3-109">如果出现错误或**GetPAB**返回零或为空，请不要继续。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-109">If there is an error or **GetPAB** returns zero or NULL, do not continue.</span></span> 
    
   ```cpp
    LPENTRYID peidPAB = NULL;
    ULONG cbeidPAB = 0;
    lpIAddrBook->GetPAB(&cbeidPAB, &peidPAB);
   ```

3. <span data-ttu-id="3bbf3-110">调用[IAddrBook::OpenEntry](iaddrbook-openentry.md)打开 PAB。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-110">Call [IAddrBook::OpenEntry](iaddrbook-openentry.md) to open the PAB.</span></span> <span data-ttu-id="3bbf3-111">_UlObjType_输出参数应设置为 MAPI_ABCONT。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-111">The  _ulObjType_ output parameter should be set to MAPI_ABCONT.</span></span> 
    
   ```cpp
    ULONG ulObjType = 0;
    LPABCONT lpPABCont = NULL;
    lpIAddrBook->OpenEntry(cbeidPAB, peidPAB,
                    NULL,
                    MAPI_MODIFY,
                    &ulObjType,
                    &lpPABCont);
   ```

4. <span data-ttu-id="3bbf3-112">调用 PAB [IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索 PR_DEF_CREATE_DL 属性，它使用创建通讯组列表的模板。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-112">Call the PAB's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the PR_DEF_CREATE_DL property, the template that it uses to create a distribution list.</span></span> 
    
   ```cpp
    lpPABCont->GetProps(0,
                tagaDefaultDL,
                &lpspvDefDLTpl);
    
   ```

5. <span data-ttu-id="3bbf3-113">如果**GetProps**失败：</span><span class="sxs-lookup"><span data-stu-id="3bbf3-113">If **GetProps** fails:</span></span> 
    
   1. <span data-ttu-id="3bbf3-114">调用 PAB [IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法使用**IMAPITable**接口打开**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-114">Call the PAB's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to open the **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) property with the **IMAPITable** interface.</span></span> 
      
   2. <span data-ttu-id="3bbf3-115">创建属性限制搜索行与**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 列等于"MAPIPDL。"</span><span class="sxs-lookup"><span data-stu-id="3bbf3-115">Create a property restriction to search for the row with the **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) column equal to "MAPIPDL."</span></span> 
      
   3. <span data-ttu-id="3bbf3-116">调用[IMAPITable::FindRow](imapitable-findrow.md)以找到此行。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-116">Call [IMAPITable::FindRow](imapitable-findrow.md) to locate this row.</span></span> 
    
6. <span data-ttu-id="3bbf3-117">保存由**GetProps**或**FindRow**返回的项标识符。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-117">Save the entry identifier returned by either **GetProps** or **FindRow**.</span></span>
    
   ```cpp
    peidDefDLTpl = lpspvDefDLTpl->Value.bin.pb;
    cbeidDefDLTpl = lpspvDefDLTpl->Value.bin.cb;
    
   ```

7. <span data-ttu-id="3bbf3-118">调用 PAB [IABContainer::CreateEntry](iabcontainer-createentry.md)方法，以创建新的项使用由已保存的项标识符的模板。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-118">Call the PAB's [IABContainer::CreateEntry](iabcontainer-createentry.md) method to create a new entry using the template represented by the saved entry identifier.</span></span> <span data-ttu-id="3bbf3-119">不要假定返回的对象将是通讯组列表，而不是邮件用户，此呼叫为远程类型时。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-119">Do not assume that the object returned will be a distribution list rather than a messaging user when this call is remoted.</span></span> <span data-ttu-id="3bbf3-120">请注意，防止输入两次添加_ulFlags_参数中传递 CREATE_CHECK_DUP 标志。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-120">Notice that the CREATE_CHECK_DUP flag is passed in the  _ulFlags_ parameter to prevent the entry from being added twice.</span></span> 
    
   ```cpp
    lpPABCont->CreateEntry(cbeidDefDLTpl,
                    peidDefDLTPL,
                    CREATE_CHECK_DUP_STRICT,
                    &lpNewPABEntry);
   ```

8. <span data-ttu-id="3bbf3-121">调用新条目的**IUnknown::QueryInterface**方法，将作为接口标识符，以确定是否条目是通讯组列表，以及支持传递 IID_IDistList [IDistList: IMAPIContainer](idistlistimapicontainer.md)接口。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-121">Call the new entry's **IUnknown::QueryInterface** method, passing IID_IDistList as the interface identifier, to determine if the entry is a distribution list and supports the [IDistList : IMAPIContainer](idistlistimapicontainer.md) interface.</span></span> <span data-ttu-id="3bbf3-122">由于**CreateEntry**返回**IMAPIProp**指针，而不是更具体的**IMailUser**或**IDistList**指针，检查已创建通讯组列表对象。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-122">Because **CreateEntry** returns an **IMAPIProp** pointer rather than the more specific **IMailUser** or **IDistList** pointer, check that a distribution list object was created.</span></span> <span data-ttu-id="3bbf3-123">如果**QueryInterface**成功，您可以确保您已创建通讯组列表，而不是邮件用户。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-123">If **QueryInterface** succeeds, you can be sure that you have created a distribution list rather than a messaging user.</span></span> 
    
9. <span data-ttu-id="3bbf3-124">调用该通讯组列表[IMAPIProp::SetProps](imapiprop-setprops.md)方法，以设置其显示名称和其他属性。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-124">Call the distribution list's [IMAPIProp::SetProps](imapiprop-setprops.md) method to set its display name and other properties.</span></span> 
    
10. <span data-ttu-id="3bbf3-125">调用该通讯组列表[IABContainer::CreateEntry](iabcontainer-createentry.md)方法，以添加一个或多个邮件用户。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-125">Call the distribution list's [IABContainer::CreateEntry](iabcontainer-createentry.md) method to add one or more messaging users.</span></span> 
    
11. <span data-ttu-id="3bbf3-126">您已经准备将其保存时调用的通讯组列表[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-126">Call the distribution list's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method when you're ready to save it.</span></span> <span data-ttu-id="3bbf3-127">若要检索的已保存的通讯组列表项标识符，设置 KEEP_OPEN_READWRITE 标记，然后调用[IMAPIProp::GetProps](imapiprop-getprops.md)请求**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-127">To retrieve the entry identifier of the saved distribution list, set the KEEP_OPEN_READWRITE flag and then call [IMAPIProp::GetProps](imapiprop-getprops.md) requesting the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
    
12. <span data-ttu-id="3bbf3-128">通过调用其**IUnknown::Release**方法释放新通讯组列表和 PAB。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-128">Release the new distribution list and the PAB by calling their **IUnknown::Release** methods.</span></span> 
    
13. <span data-ttu-id="3bbf3-129">调用[MAPIFreeBuffer](mapifreebuffer.md)释放 PAB 和调整的属性标记数组的项标识符的内存。</span><span class="sxs-lookup"><span data-stu-id="3bbf3-129">Call [MAPIFreeBuffer](mapifreebuffer.md) to release the memory for the entry identifier of the PAB and the sized property tag array.</span></span> 
    

