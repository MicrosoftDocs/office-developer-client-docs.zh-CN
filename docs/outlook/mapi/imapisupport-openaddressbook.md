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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e9cd1c7ce0983a47311b2626cc3b40b47748b951
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775643"
---
# <a name="imapisupportopenaddressbook"></a><span data-ttu-id="26a6a-103">IMAPISupport::OpenAddressBook</span><span class="sxs-lookup"><span data-stu-id="26a6a-103">IMAPISupport::OpenAddressBook</span></span>

  
  
<span data-ttu-id="26a6a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="26a6a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="26a6a-105">提供对通讯簿访问。</span><span class="sxs-lookup"><span data-stu-id="26a6a-105">Provides access to the address book.</span></span>
  
```cpp
HRESULT OpenAddressBook(
LPCIID lpInterface,
ULONG ulFlags,
LPADRBOOK FAR * lppAdrBook
);
```

## <a name="parameters"></a><span data-ttu-id="26a6a-106">参数</span><span class="sxs-lookup"><span data-stu-id="26a6a-106">Parameters</span></span>

 <span data-ttu-id="26a6a-107">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="26a6a-107">_lpInterface_</span></span>
  
> <span data-ttu-id="26a6a-108">[in]指向接口标识 (IID) 值，该值代表要用于访问通讯簿的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="26a6a-108">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the address book.</span></span> <span data-ttu-id="26a6a-109">有效值为 NULL，表明标准地址簿接口[IAddrBook](iaddrbookimapiprop.md)和 IID_IAddrBook。</span><span class="sxs-lookup"><span data-stu-id="26a6a-109">Valid values are NULL, which indicates the standard address book interface [IAddrBook](iaddrbookimapiprop.md), and IID_IAddrBook.</span></span>
    
 <span data-ttu-id="26a6a-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="26a6a-110">_ulFlags_</span></span>
  
> <span data-ttu-id="26a6a-111">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="26a6a-111">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="26a6a-112">_lppAdrBook_</span><span class="sxs-lookup"><span data-stu-id="26a6a-112">_lppAdrBook_</span></span>
  
> <span data-ttu-id="26a6a-113">[输出]指向与通讯簿的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="26a6a-113">[out] A pointer to a pointer to the address book.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="26a6a-114">返回值</span><span class="sxs-lookup"><span data-stu-id="26a6a-114">Return value</span></span>

<span data-ttu-id="26a6a-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="26a6a-115">S_OK</span></span> 
  
> <span data-ttu-id="26a6a-116">提供对通讯簿的访问。</span><span class="sxs-lookup"><span data-stu-id="26a6a-116">Access to the address book was provided.</span></span>
    
<span data-ttu-id="26a6a-117">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="26a6a-117">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="26a6a-118">调用成功，但无法加载一个或多个地址簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="26a6a-118">The call succeeded, but one or more address book providers could not be loaded.</span></span> <span data-ttu-id="26a6a-119">返回此警告时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="26a6a-119">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="26a6a-120">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="26a6a-120">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="26a6a-121">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="26a6a-121">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="26a6a-122">说明</span><span class="sxs-lookup"><span data-stu-id="26a6a-122">Remarks</span></span>

<span data-ttu-id="26a6a-123">**IMAPISupport::OpenAddressBook**方法将执行所有服务提供商支持对象。</span><span class="sxs-lookup"><span data-stu-id="26a6a-123">The **IMAPISupport::OpenAddressBook** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="26a6a-124">服务提供商，通常紧密耦合的消息存储和传输提供程序，调用**OpenAddressBook**才能访问通讯簿。</span><span class="sxs-lookup"><span data-stu-id="26a6a-124">Service providers, typically tightly coupled message store and transport providers, call **OpenAddressBook** to get access to the address book.</span></span> <span data-ttu-id="26a6a-125">返回的**IAddrBook**指针可用于各种地址簿任务，包括打开通讯簿容器，查找邮件用户和显示地址对话框。</span><span class="sxs-lookup"><span data-stu-id="26a6a-125">The returned **IAddrBook** pointer can be used for a variety of address book tasks, including opening address book containers, finding messaging users, and displaying address dialog boxes.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="26a6a-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="26a6a-126">Notes to callers</span></span>

 <span data-ttu-id="26a6a-127">**OpenAddressBook**可以返回 MAPI_W_ERRORS_RETURNED，如果它无法加载一个或多个当前配置文件中的地址簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="26a6a-127">**OpenAddressBook** can return MAPI_W_ERRORS_RETURNED if it cannot load one or more of the address book providers in the current profile.</span></span> <span data-ttu-id="26a6a-128">此值是一条警告，您应视为呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="26a6a-128">This value is a warning and you should treat the call as successful.</span></span> <span data-ttu-id="26a6a-129">即使所有通讯簿提供程序无法加载， **OpenAddressBook**仍成功， _lppAdrBook_参数中返回 MAPI_W_ERRORS_RETURNED 和**IAddrBook**指针。</span><span class="sxs-lookup"><span data-stu-id="26a6a-129">Even if all of the address book providers failed to load, **OpenAddressBook** still succeeds, returning MAPI_W_ERRORS_RETURNED and an **IAddrBook** pointer in the  _lppAdrBook_ parameter.</span></span> <span data-ttu-id="26a6a-130">由于**OpenAddressBook**始终返回有效的**IAddrBook**指针，您必须释放其完后使用它。</span><span class="sxs-lookup"><span data-stu-id="26a6a-130">Because **OpenAddressBook** always returns a valid **IAddrBook** pointer, you must release it when you are finished using it.</span></span> 
  
<span data-ttu-id="26a6a-131">如果一个或多个地址簿提供程序无法加载，调用[IMAPISupport::GetLastError](imapisupport-getlasterror.md)获取[MAPIERROR](mapierror.md)结构，其中包含系统未加载提供程序的信息。</span><span class="sxs-lookup"><span data-stu-id="26a6a-131">If one or more address book providers failed to load, call [IMAPISupport::GetLastError](imapisupport-getlasterror.md) to obtain a [MAPIERROR](mapierror.md) structure that contains information about the providers that did not load.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="26a6a-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26a6a-132">See also</span></span>



[<span data-ttu-id="26a6a-133">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="26a6a-133">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)
  
[<span data-ttu-id="26a6a-134">IMAPISession::OpenAddressBook</span><span class="sxs-lookup"><span data-stu-id="26a6a-134">IMAPISession::OpenAddressBook</span></span>](imapisession-openaddressbook.md)
  
[<span data-ttu-id="26a6a-135">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="26a6a-135">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

