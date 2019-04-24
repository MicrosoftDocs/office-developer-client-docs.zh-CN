---
title: IMAPISessionOpenAddressBook
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.OpenAddressBook
api_type:
- COM
ms.assetid: 2b6a4c6a-bb71-4ea1-a3b6-90a2722880fb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 51bf5f8455d4cb790d0c955e96249b0f9deef1af
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329419"
---
# <a name="imapisessionopenaddressbook"></a><span data-ttu-id="56777-103">IMAPISession::OpenAddressBook</span><span class="sxs-lookup"><span data-stu-id="56777-103">IMAPISession::OpenAddressBook</span></span>

  
  
<span data-ttu-id="56777-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="56777-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="56777-105">打开 MAPI 集成通讯簿, 返回一个[IAddrBook](iaddrbookimapiprop.md)指针以供进一步访问。</span><span class="sxs-lookup"><span data-stu-id="56777-105">Opens the MAPI integrated address book, returning an [IAddrBook](iaddrbookimapiprop.md) pointer for further access.</span></span> 
  
```cpp
HRESULT OpenAddressBook(
  ULONG_PTR ulUIParam,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPADRBOOK FAR * lppAdrBook
);
```

## <a name="parameters"></a><span data-ttu-id="56777-106">参数</span><span class="sxs-lookup"><span data-stu-id="56777-106">Parameters</span></span>

 <span data-ttu-id="56777-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="56777-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="56777-108">实时公用地址对话框和其他相关显示的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="56777-108">[in] A handle to the parent window of the common address dialog box and other related displays.</span></span>
    
 <span data-ttu-id="56777-109">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="56777-109">_lpInterface_</span></span>
  
> <span data-ttu-id="56777-110">实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问通讯簿的接口。</span><span class="sxs-lookup"><span data-stu-id="56777-110">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the address book.</span></span> <span data-ttu-id="56777-111">传递**null**将返回指向通讯簿的标准接口 ( [IAddrBook: IMAPIProp](iaddrbookimapiprop.md)) 的指针。</span><span class="sxs-lookup"><span data-stu-id="56777-111">Passing **null** returns a pointer to the address book's standard interface, [IAddrBook : IMAPIProp](iaddrbookimapiprop.md).</span></span> 
    
 <span data-ttu-id="56777-112">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="56777-112">_ulFlags_</span></span>
  
> <span data-ttu-id="56777-113">实时控制通讯簿的打开的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="56777-113">[in] A bitmask of flags that controls the opening of the address book.</span></span> <span data-ttu-id="56777-114">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="56777-114">The following flag can be set:</span></span>
    
<span data-ttu-id="56777-115">AB_NO_DIALOG</span><span class="sxs-lookup"><span data-stu-id="56777-115">AB_NO_DIALOG</span></span> 
  
> <span data-ttu-id="56777-116">禁止显示对话框。</span><span class="sxs-lookup"><span data-stu-id="56777-116">Suppresses the display of dialog boxes.</span></span> <span data-ttu-id="56777-117">如果未设置 AB_NO_DIALOG 标志, 则参与集成通讯簿的通讯簿提供程序可以提示用户输入任何必要的信息。</span><span class="sxs-lookup"><span data-stu-id="56777-117">If the AB_NO_DIALOG flag is not set, the address book providers that contribute to the integrated address book can prompt the user for any necessary information.</span></span> 
    
 <span data-ttu-id="56777-118">_lppAdrBook_</span><span class="sxs-lookup"><span data-stu-id="56777-118">_lppAdrBook_</span></span>
  
> <span data-ttu-id="56777-119">排除指向通讯簿的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="56777-119">[out] A pointer to a pointer to the address book.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="56777-120">返回值</span><span class="sxs-lookup"><span data-stu-id="56777-120">Return value</span></span>

<span data-ttu-id="56777-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="56777-121">S_OK</span></span> 
  
> <span data-ttu-id="56777-122">已成功打开通讯簿。</span><span class="sxs-lookup"><span data-stu-id="56777-122">The address book was successfully opened.</span></span>
    
<span data-ttu-id="56777-123">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="56777-123">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="56777-124">调用成功, 但无法打开一个或多个通讯簿提供程序的容器。</span><span class="sxs-lookup"><span data-stu-id="56777-124">The call succeeded, but the containers of one or more address book providers could not be opened.</span></span> <span data-ttu-id="56777-125">返回此警告时, 应以成功的方式处理该调用。</span><span class="sxs-lookup"><span data-stu-id="56777-125">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="56777-126">若要测试此警告, 请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="56777-126">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="56777-127">有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="56777-127">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="56777-128">注解</span><span class="sxs-lookup"><span data-stu-id="56777-128">Remarks</span></span>

<span data-ttu-id="56777-129">**IMAPISession:: OpenAddressBook**方法打开 MAPI 集成通讯簿, 即配置文件中所有通讯簿提供程序的顶级容器的集合。</span><span class="sxs-lookup"><span data-stu-id="56777-129">The **IMAPISession::OpenAddressBook** method opens the MAPI integrated address book, a collection of the top-level containers of all of the address book providers in the profile.</span></span> <span data-ttu-id="56777-130">在_lppAdrBook_参数中返回的指针提供了对通讯簿内容的进一步访问权限。</span><span class="sxs-lookup"><span data-stu-id="56777-130">The pointer that is returned in the  _lppAdrBook_ parameter provides further access to the contents of the address book.</span></span> <span data-ttu-id="56777-131">这样, 调用方可以执行以下任务: 打开单个容器、查找邮件用户和显示常用地址对话框。</span><span class="sxs-lookup"><span data-stu-id="56777-131">This allows the caller to perform tasks such as opening individual containers, finding messaging users, and displaying common address dialog boxes.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="56777-132">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="56777-132">Notes to callers</span></span>

 <span data-ttu-id="56777-133">如果不能在配置文件中加载一个或多个通讯簿提供程序, **OpenAddressBook**将返回 MAPI_W_ERRORS_RETURNED。</span><span class="sxs-lookup"><span data-stu-id="56777-133">**OpenAddressBook** returns MAPI_W_ERRORS_RETURNED if it cannot load one or more of the address book providers in the profile.</span></span> <span data-ttu-id="56777-134">此值是一个警告, 而不是错误值;就像 S_OK 那样处理它。</span><span class="sxs-lookup"><span data-stu-id="56777-134">This value is a warning, not an error value; handle it as you would S_OK.</span></span> <span data-ttu-id="56777-135">**OpenAddressBook**始终返回_lppAdrBook_参数中的有效指针, 而不考虑加载多少通讯簿提供程序无法加载。</span><span class="sxs-lookup"><span data-stu-id="56777-135">**OpenAddressBook** always returns a valid pointer in the  _lppAdrBook_ parameter, regardless of how many of the address book providers failed to load.</span></span> <span data-ttu-id="56777-136">因此, 在注销之前, 必须始终在某个时刻调用通讯簿[IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="56777-136">Therefore, you must always call the address book's [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) method at some point before logging off.</span></span> 
  
<span data-ttu-id="56777-137">当**OpenAddressBook**返回 MAPI_W_ERRORS_RETURNED 时, 调用[IMAPISession:: GetLastError](imapisession-getlasterror.md)获取包含有关失败的提供程序的信息的[MAPIERROR](mapierror.md)结构。</span><span class="sxs-lookup"><span data-stu-id="56777-137">When **OpenAddressBook** returns MAPI_W_ERRORS_RETURNED, call [IMAPISession::GetLastError](imapisession-getlasterror.md) to obtain a [MAPIERROR](mapierror.md) structure that contains information about the failing providers.</span></span> <span data-ttu-id="56777-138">返回一个**MAPIERROR**结构, 其中包含所有提供程序提供的信息。</span><span class="sxs-lookup"><span data-stu-id="56777-138">A single **MAPIERROR** structure is returned that contains information supplied by all of the providers.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="56777-139">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="56777-139">MFCMAPI reference</span></span>

<span data-ttu-id="56777-140">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="56777-140">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="56777-141">**文件**</span><span class="sxs-lookup"><span data-stu-id="56777-141">**File**</span></span>|<span data-ttu-id="56777-142">**函数**</span><span class="sxs-lookup"><span data-stu-id="56777-142">**Function**</span></span>|<span data-ttu-id="56777-143">**备注**</span><span class="sxs-lookup"><span data-stu-id="56777-143">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="56777-144">MAPIObjects</span><span class="sxs-lookup"><span data-stu-id="56777-144">MAPIObjects.cpp</span></span>  <br/> |<span data-ttu-id="56777-145">CMapiObjects:: GetAddrBook</span><span class="sxs-lookup"><span data-stu-id="56777-145">CMapiObjects::GetAddrBook</span></span>  <br/> |<span data-ttu-id="56777-146">MFCMAPI 使用**IMAPISession:: OpenAddressBook**方法获取集成的通讯簿。</span><span class="sxs-lookup"><span data-stu-id="56777-146">MFCMAPI uses the **IMAPISession::OpenAddressBook** method to obtain the integrated address book.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="56777-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56777-147">See also</span></span>



[<span data-ttu-id="56777-148">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="56777-148">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)
  
[<span data-ttu-id="56777-149">IMAPISession::GetLastError</span><span class="sxs-lookup"><span data-stu-id="56777-149">IMAPISession::GetLastError</span></span>](imapisession-getlasterror.md)
  
[<span data-ttu-id="56777-150">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="56777-150">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="56777-151">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="56777-151">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="56777-152">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="56777-152">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

