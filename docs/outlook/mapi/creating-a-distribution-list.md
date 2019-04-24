---
title: 创建通讯组列表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b63a6024-910d-4569-a3b4-c3ebf0b32c3d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7108ae215562169244100a56cc9b9208d78b1893
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32333024"
---
# <a name="creating-a-distribution-list"></a><span data-ttu-id="3f03b-103">创建通讯组列表</span><span class="sxs-lookup"><span data-stu-id="3f03b-103">Creating a distribution list</span></span>

<span data-ttu-id="3f03b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3f03b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3f03b-105">客户端可直接在可修改的容器 (如个人通讯簿 (PAB)) 中创建通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="3f03b-105">Clients can create a distribution list directly into a modifiable container such as the personal address book (PAB).</span></span>
  
<span data-ttu-id="3f03b-106">**在 PAB 中创建通讯组列表**</span><span class="sxs-lookup"><span data-stu-id="3f03b-106">**To create a distribution list in the PAB**</span></span>
  
1. <span data-ttu-id="3f03b-107">创建具有一个属性标记的大小的属性标记数组, **PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md)), 如下所示:</span><span class="sxs-lookup"><span data-stu-id="3f03b-107">Create a sized property tag array with one property tag, **PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md)), as follows:</span></span>
    
   ```cpp
    SizedPropTagArray(1, tagaDefaultDL) =
    {
        1,
        {
            PR_DEF_CREATE_DL
        }
    };
   ```

2. <span data-ttu-id="3f03b-108">调用[IAddrBook:: GetPAB](iaddrbook-getpab.md)以检索 PAB 的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="3f03b-108">Call [IAddrBook::GetPAB](iaddrbook-getpab.md) to retrieve the entry identifier of the PAB.</span></span> <span data-ttu-id="3f03b-109">如果有错误或**GetPAB**返回零或 NULL, 则不会继续。</span><span class="sxs-lookup"><span data-stu-id="3f03b-109">If there is an error or **GetPAB** returns zero or NULL, do not continue.</span></span> 
    
   ```cpp
    LPENTRYID peidPAB = NULL;
    ULONG cbeidPAB = 0;
    lpIAddrBook->GetPAB(&cbeidPAB, &peidPAB);
   ```

3. <span data-ttu-id="3f03b-110">调用[IAddrBook:: OpenEntry](iaddrbook-openentry.md)以打开 PAB。</span><span class="sxs-lookup"><span data-stu-id="3f03b-110">Call [IAddrBook::OpenEntry](iaddrbook-openentry.md) to open the PAB.</span></span> <span data-ttu-id="3f03b-111">_ulObjType_输出参数应设置为 MAPI_ABCONT。</span><span class="sxs-lookup"><span data-stu-id="3f03b-111">The  _ulObjType_ output parameter should be set to MAPI_ABCONT.</span></span> 
    
   ```cpp
    ULONG ulObjType = 0;
    LPABCONT lpPABCont = NULL;
    lpIAddrBook->OpenEntry(cbeidPAB, peidPAB,
                    NULL,
                    MAPI_MODIFY,
                    &ulObjType,
                    &lpPABCont);
   ```

4. <span data-ttu-id="3f03b-112">调用 PAB 的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索 PR_DEF_CREATE_DL 属性, 它用于创建通讯组列表的模板。</span><span class="sxs-lookup"><span data-stu-id="3f03b-112">Call the PAB's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the PR_DEF_CREATE_DL property, the template that it uses to create a distribution list.</span></span> 
    
   ```cpp
    lpPABCont->GetProps(0,
                tagaDefaultDL,
                &lpspvDefDLTpl);
    
   ```

5. <span data-ttu-id="3f03b-113">如果**GetProps**失败:</span><span class="sxs-lookup"><span data-stu-id="3f03b-113">If **GetProps** fails:</span></span> 
    
   1. <span data-ttu-id="3f03b-114">调用 PAB 的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法, 以使用**IMAPITable**接口打开**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="3f03b-114">Call the PAB's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to open the **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) property with the **IMAPITable** interface.</span></span> 
      
   2. <span data-ttu-id="3f03b-115">创建属性限制以搜索**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 列等于 "MAPIPDL" 的行。</span><span class="sxs-lookup"><span data-stu-id="3f03b-115">Create a property restriction to search for the row with the **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) column equal to "MAPIPDL."</span></span> 
      
   3. <span data-ttu-id="3f03b-116">调用[IMAPITable:: FindRow](imapitable-findrow.md)以查找此行。</span><span class="sxs-lookup"><span data-stu-id="3f03b-116">Call [IMAPITable::FindRow](imapitable-findrow.md) to locate this row.</span></span> 
    
6. <span data-ttu-id="3f03b-117">保存由**GetProps**或**FindRow**返回的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="3f03b-117">Save the entry identifier returned by either **GetProps** or **FindRow**.</span></span>
    
   ```cpp
    peidDefDLTpl = lpspvDefDLTpl->Value.bin.pb;
    cbeidDefDLTpl = lpspvDefDLTpl->Value.bin.cb;
    
   ```

7. <span data-ttu-id="3f03b-118">调用 PAB 的[IABContainer:: CreateEntry](iabcontainer-createentry.md)方法, 以使用已保存的条目标识符表示的模板创建新条目。</span><span class="sxs-lookup"><span data-stu-id="3f03b-118">Call the PAB's [IABContainer::CreateEntry](iabcontainer-createentry.md) method to create a new entry using the template represented by the saved entry identifier.</span></span> <span data-ttu-id="3f03b-119">不要假定返回的对象将是通讯组列表, 而不是消息用户 (当此调用是远程的时)。</span><span class="sxs-lookup"><span data-stu-id="3f03b-119">Do not assume that the object returned will be a distribution list rather than a messaging user when this call is remoted.</span></span> <span data-ttu-id="3f03b-120">请注意, CREATE_CHECK_DUP 标志在_ulFlags_参数中传递, 以防止添加两次输入。</span><span class="sxs-lookup"><span data-stu-id="3f03b-120">Notice that the CREATE_CHECK_DUP flag is passed in the  _ulFlags_ parameter to prevent the entry from being added twice.</span></span> 
    
   ```cpp
    lpPABCont->CreateEntry(cbeidDefDLTpl,
                    peidDefDLTPL,
                    CREATE_CHECK_DUP_STRICT,
                    &lpNewPABEntry);
   ```

8. <span data-ttu-id="3f03b-121">调用新条目的**IUnknown:: QueryInterface**方法, 将 IID_IDistList 作为接口标识符传递, 以确定该条目是否为通讯组列表并支持[IDistList: IMAPIContainer](idistlistimapicontainer.md)接口。</span><span class="sxs-lookup"><span data-stu-id="3f03b-121">Call the new entry's **IUnknown::QueryInterface** method, passing IID_IDistList as the interface identifier, to determine if the entry is a distribution list and supports the [IDistList : IMAPIContainer](idistlistimapicontainer.md) interface.</span></span> <span data-ttu-id="3f03b-122">由于**CreateEntry**返回**IMAPIProp**指针, 而不是更具体的**IMailUser**或**IDistList**指针, 请检查是否已创建通讯组列表对象。</span><span class="sxs-lookup"><span data-stu-id="3f03b-122">Because **CreateEntry** returns an **IMAPIProp** pointer rather than the more specific **IMailUser** or **IDistList** pointer, check that a distribution list object was created.</span></span> <span data-ttu-id="3f03b-123">如果**QueryInterface**成功, 则可以确保已创建了通讯组列表, 而不是邮件用户。</span><span class="sxs-lookup"><span data-stu-id="3f03b-123">If **QueryInterface** succeeds, you can be sure that you have created a distribution list rather than a messaging user.</span></span> 
    
9. <span data-ttu-id="3f03b-124">调用通讯组列表的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法以设置其显示名称和其他属性。</span><span class="sxs-lookup"><span data-stu-id="3f03b-124">Call the distribution list's [IMAPIProp::SetProps](imapiprop-setprops.md) method to set its display name and other properties.</span></span> 
    
10. <span data-ttu-id="3f03b-125">调用通讯组列表的[IABContainer:: CreateEntry](iabcontainer-createentry.md)方法以添加一个或多个邮件用户。</span><span class="sxs-lookup"><span data-stu-id="3f03b-125">Call the distribution list's [IABContainer::CreateEntry](iabcontainer-createentry.md) method to add one or more messaging users.</span></span> 
    
11. <span data-ttu-id="3f03b-126">当您准备好保存通讯组列表的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法时, 调用该方法。</span><span class="sxs-lookup"><span data-stu-id="3f03b-126">Call the distribution list's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method when you're ready to save it.</span></span> <span data-ttu-id="3f03b-127">若要检索已保存的通讯组列表的条目标识符, 请设置 KEEP_OPEN_READWRITE 标志, 然后调用[IMAPIProp:: GetProps](imapiprop-getprops.md)请求**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="3f03b-127">To retrieve the entry identifier of the saved distribution list, set the KEEP_OPEN_READWRITE flag and then call [IMAPIProp::GetProps](imapiprop-getprops.md) requesting the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
    
12. <span data-ttu-id="3f03b-128">通过调用其**IUnknown:: release**方法来释放新的通讯组列表和 PAB。</span><span class="sxs-lookup"><span data-stu-id="3f03b-128">Release the new distribution list and the PAB by calling their **IUnknown::Release** methods.</span></span> 
    
13. <span data-ttu-id="3f03b-129">调用[MAPIFreeBuffer](mapifreebuffer.md)以释放 PAB 条目标识符和大小属性标记数组的内存。</span><span class="sxs-lookup"><span data-stu-id="3f03b-129">Call [MAPIFreeBuffer](mapifreebuffer.md) to release the memory for the entry identifier of the PAB and the sized property tag array.</span></span> 
    

