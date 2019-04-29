---
title: IMAPISupportOpenAddressBook
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.OpenAddressBook
api_type:
- COM
ms.assetid: d8da8be1-3efe-410a-bcce-49e522602d80
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 47a62b331ff9f1c96576d42797ebb23ed61cd362
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416879"
---
# <a name="imapisupportopenaddressbook"></a><span data-ttu-id="9a6de-103">IMAPISupport::OpenAddressBook</span><span class="sxs-lookup"><span data-stu-id="9a6de-103">IMAPISupport::OpenAddressBook</span></span>

  
  
<span data-ttu-id="9a6de-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9a6de-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9a6de-105">提供对通讯簿的访问权限。</span><span class="sxs-lookup"><span data-stu-id="9a6de-105">Provides access to the address book.</span></span>
  
```cpp
HRESULT OpenAddressBook(
LPCIID lpInterface,
ULONG ulFlags,
LPADRBOOK FAR * lppAdrBook
);
```

## <a name="parameters"></a><span data-ttu-id="9a6de-106">参数</span><span class="sxs-lookup"><span data-stu-id="9a6de-106">Parameters</span></span>

 <span data-ttu-id="9a6de-107">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="9a6de-107">_lpInterface_</span></span>
  
> <span data-ttu-id="9a6de-108">实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问通讯簿的接口。</span><span class="sxs-lookup"><span data-stu-id="9a6de-108">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the address book.</span></span> <span data-ttu-id="9a6de-109">有效的值为 NULL, 表示标准通讯簿接口[IAddrBook](iaddrbookimapiprop.md)和 IID_IAddrBook。</span><span class="sxs-lookup"><span data-stu-id="9a6de-109">Valid values are NULL, which indicates the standard address book interface [IAddrBook](iaddrbookimapiprop.md), and IID_IAddrBook.</span></span>
    
 <span data-ttu-id="9a6de-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="9a6de-110">_ulFlags_</span></span>
  
> <span data-ttu-id="9a6de-111">保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="9a6de-111">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="9a6de-112">_lppAdrBook_</span><span class="sxs-lookup"><span data-stu-id="9a6de-112">_lppAdrBook_</span></span>
  
> <span data-ttu-id="9a6de-113">排除指向通讯簿的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="9a6de-113">[out] A pointer to a pointer to the address book.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9a6de-114">返回值</span><span class="sxs-lookup"><span data-stu-id="9a6de-114">Return value</span></span>

<span data-ttu-id="9a6de-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a6de-115">S_OK</span></span> 
  
> <span data-ttu-id="9a6de-116">提供了对通讯簿的访问权限。</span><span class="sxs-lookup"><span data-stu-id="9a6de-116">Access to the address book was provided.</span></span>
    
<span data-ttu-id="9a6de-117">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="9a6de-117">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="9a6de-118">呼叫成功, 但无法加载一个或多个通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="9a6de-118">The call succeeded, but one or more address book providers could not be loaded.</span></span> <span data-ttu-id="9a6de-119">返回此警告时, 应以成功的方式处理该调用。</span><span class="sxs-lookup"><span data-stu-id="9a6de-119">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="9a6de-120">若要测试此警告, 请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="9a6de-120">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="9a6de-121">有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="9a6de-121">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9a6de-122">说明</span><span class="sxs-lookup"><span data-stu-id="9a6de-122">Remarks</span></span>

<span data-ttu-id="9a6de-123">**IMAPISupport:: OpenAddressBook**方法是为所有服务提供程序支持对象实现的。</span><span class="sxs-lookup"><span data-stu-id="9a6de-123">The **IMAPISupport::OpenAddressBook** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="9a6de-124">服务提供商 (通常是紧密耦合的邮件存储和传输提供程序) 调用**OpenAddressBook**以获取对通讯簿的访问权限。</span><span class="sxs-lookup"><span data-stu-id="9a6de-124">Service providers, typically tightly coupled message store and transport providers, call **OpenAddressBook** to get access to the address book.</span></span> <span data-ttu-id="9a6de-125">返回的**IAddrBook**指针可用于各种通讯簿任务, 包括打开通讯簿容器、查找邮件用户和显示地址对话框。</span><span class="sxs-lookup"><span data-stu-id="9a6de-125">The returned **IAddrBook** pointer can be used for a variety of address book tasks, including opening address book containers, finding messaging users, and displaying address dialog boxes.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="9a6de-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="9a6de-126">Notes to callers</span></span>

 <span data-ttu-id="9a6de-127">如果**OpenAddressBook**无法在当前配置文件中加载一个或多个通讯簿提供程序, 则可以返回 MAPI_W_ERRORS_RETURNED。</span><span class="sxs-lookup"><span data-stu-id="9a6de-127">**OpenAddressBook** can return MAPI_W_ERRORS_RETURNED if it cannot load one or more of the address book providers in the current profile.</span></span> <span data-ttu-id="9a6de-128">此值是一个警告, 应将呼叫视为 "成功"。</span><span class="sxs-lookup"><span data-stu-id="9a6de-128">This value is a warning and you should treat the call as successful.</span></span> <span data-ttu-id="9a6de-129">即使所有通讯簿提供程序加载失败, **OpenAddressBook**仍会成功, 并在_lppAdrBook_参数中返回 MAPI_W_ERRORS_RETURNED 和**IAddrBook**指针。</span><span class="sxs-lookup"><span data-stu-id="9a6de-129">Even if all of the address book providers failed to load, **OpenAddressBook** still succeeds, returning MAPI_W_ERRORS_RETURNED and an **IAddrBook** pointer in the  _lppAdrBook_ parameter.</span></span> <span data-ttu-id="9a6de-130">由于**OpenAddressBook**始终返回有效的**IAddrBook**指针, 因此您必须在使用完它后将其释放。</span><span class="sxs-lookup"><span data-stu-id="9a6de-130">Because **OpenAddressBook** always returns a valid **IAddrBook** pointer, you must release it when you are finished using it.</span></span> 
  
<span data-ttu-id="9a6de-131">如果一个或多个通讯簿提供程序加载失败, 请调用[IMAPISupport:: GetLastError](imapisupport-getlasterror.md)获取包含有关未加载的提供程序的信息的[MAPIERROR](mapierror.md)结构。</span><span class="sxs-lookup"><span data-stu-id="9a6de-131">If one or more address book providers failed to load, call [IMAPISupport::GetLastError](imapisupport-getlasterror.md) to obtain a [MAPIERROR](mapierror.md) structure that contains information about the providers that did not load.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9a6de-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a6de-132">See also</span></span>



[<span data-ttu-id="9a6de-133">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="9a6de-133">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)
  
[<span data-ttu-id="9a6de-134">IMAPISession::OpenAddressBook</span><span class="sxs-lookup"><span data-stu-id="9a6de-134">IMAPISession::OpenAddressBook</span></span>](imapisession-openaddressbook.md)
  
[<span data-ttu-id="9a6de-135">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9a6de-135">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

