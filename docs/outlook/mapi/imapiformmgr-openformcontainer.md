---
title: IMAPIFormMgrOpenFormContainer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.OpenFormContainer
api_type:
- COM
ms.assetid: df02bdc5-903a-4ce2-9f43-5f4513ea19b3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 68a358c91e35c5a075e220794c78f4e5c96e43ee
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321635"
---
# <a name="imapiformmgropenformcontainer"></a><span data-ttu-id="c7634-103">IMAPIFormMgr::OpenFormContainer</span><span class="sxs-lookup"><span data-stu-id="c7634-103">IMAPIFormMgr::OpenFormContainer</span></span>

  
  
<span data-ttu-id="c7634-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c7634-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c7634-105">打开特定表单容器的 [IMAPIFormContainer](imapiformcontaineriunknown.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="c7634-105">Opens an [IMAPIFormContainer](imapiformcontaineriunknown.md) interface for a specific form container.</span></span> 
  
```cpp
HRESULT OpenFormContainer(
  HFRMREG hfrmreg,
  LPUNKNOWN lpunk,
  LPMAPIFORMCONTAINER FAR * lppfcnt
);
```

## <a name="parameters"></a><span data-ttu-id="c7634-106">参数</span><span class="sxs-lookup"><span data-stu-id="c7634-106">Parameters</span></span>

 <span data-ttu-id="c7634-107">_分贝区_</span><span class="sxs-lookup"><span data-stu-id="c7634-107">_hfrmreg_</span></span>
  
> <span data-ttu-id="c7634-108">[in]指示要打开的表单库的 (，即要打开表单的表单容器的) 。</span><span class="sxs-lookup"><span data-stu-id="c7634-108">[in] An HFRMREG enumeration that indicates the form library to open (that is, the form container to open).</span></span> <span data-ttu-id="c7634-109">一个特定于表单库提供程序的枚举。</span><span class="sxs-lookup"><span data-stu-id="c7634-109">An HFRMREG enumeration is an enumeration that is specific to a form library provider.</span></span> <span data-ttu-id="c7634-110">可能的FCRMREG 值包括：</span><span class="sxs-lookup"><span data-stu-id="c7634-110">Possible HFRMREG values include the following:</span></span>
    
<span data-ttu-id="c7634-111">HFRMREG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="c7634-111">HFRMREG_DEFAULT</span></span> 
  
> <span data-ttu-id="c7634-112">方便的表单容器。</span><span class="sxs-lookup"><span data-stu-id="c7634-112">A convenient form container.</span></span>
    
<span data-ttu-id="c7634-113">HFRMREG_FOLDER</span><span class="sxs-lookup"><span data-stu-id="c7634-113">HFRMREG_FOLDER</span></span> 
  
> <span data-ttu-id="c7634-114">文件夹容器。</span><span class="sxs-lookup"><span data-stu-id="c7634-114">A folder container.</span></span> 
    
<span data-ttu-id="c7634-115">HFRMREG_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="c7634-115">HFRMREG_PERSONAL</span></span> 
  
> <span data-ttu-id="c7634-116">默认邮件存储的容器。</span><span class="sxs-lookup"><span data-stu-id="c7634-116">The container for the default message store.</span></span> 
    
<span data-ttu-id="c7634-117">HFRMREG_LOCAL</span><span class="sxs-lookup"><span data-stu-id="c7634-117">HFRMREG_LOCAL</span></span> 
  
> <span data-ttu-id="c7634-118">本地表单容器。</span><span class="sxs-lookup"><span data-stu-id="c7634-118">A local form container.</span></span> 
    
 <span data-ttu-id="c7634-119">_lpunk_</span><span class="sxs-lookup"><span data-stu-id="c7634-119">_lpunk_</span></span>
  
> <span data-ttu-id="c7634-120">[in]指向打开接口的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="c7634-120">[in] A pointer to the object for which the interface is opened.</span></span> <span data-ttu-id="c7634-121">_lpunk_ 参数必须为 **null，** 除非 _用于该设置的参数的值_ 需要对象指针。</span><span class="sxs-lookup"><span data-stu-id="c7634-121">The  _lpunk_ parameter must be **null** unless the value for the  _hfrmreg_ parameter requires an object pointer.</span></span> 
    
 <span data-ttu-id="c7634-122">_lppfcnt_</span><span class="sxs-lookup"><span data-stu-id="c7634-122">_lppfcnt_</span></span>
  
> <span data-ttu-id="c7634-123">[out]指向返回的表单容器对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="c7634-123">[out] A pointer to a pointer to the returned form container object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c7634-124">返回值</span><span class="sxs-lookup"><span data-stu-id="c7634-124">Return value</span></span>

<span data-ttu-id="c7634-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7634-125">S_OK</span></span> 
  
> <span data-ttu-id="c7634-126">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="c7634-126">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="c7634-127">MAPI_E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="c7634-127">MAPI_E_NO_INTERFACE</span></span> 
  
> <span data-ttu-id="c7634-128">_lpunk_ 指向的对象不支持所需的接口。</span><span class="sxs-lookup"><span data-stu-id="c7634-128">The object pointed to by  _lpunk_ does not support the required interface.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="c7634-129">备注</span><span class="sxs-lookup"><span data-stu-id="c7634-129">Remarks</span></span>

<span data-ttu-id="c7634-130">表单查看器调用 **IMAPIFormMgr：：OpenFormContainer** 方法来打开特定表单容器的 **IMAPIFormContainer** 接口。</span><span class="sxs-lookup"><span data-stu-id="c7634-130">Form viewers call the **IMAPIFormMgr::OpenFormContainer** method to open an **IMAPIFormContainer** interface for a specific form container.</span></span> <span data-ttu-id="c7634-131">然后，此接口可用于将表单安装到表单容器以及从表单容器中删除表单。</span><span class="sxs-lookup"><span data-stu-id="c7634-131">This interface can then be used for installing forms into and removing forms from a form container.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="c7634-132">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="c7634-132">Notes to callers</span></span>

<span data-ttu-id="c7634-133">如果  _HFRMREG_FOLDER_ 中的值为  _HFRMREG_FOLDER，则 lpunk_ 中使用的接口标识符必须为非 **null，** 并且必须允许 [IUnknown：：QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) 方法调用 [IMAPIFolder](imapifolderimapicontainer.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="c7634-133">If the value in  _hfrmreg_ is HFRMREG_FOLDER, the interface identifier used in  _lpunk_ must be non- **null** and must allow [IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) method calls to an [IMAPIFolder](imapifolderimapicontainer.md) interface.</span></span> 
  
<span data-ttu-id="c7634-134">若要打开本地表单容器，必须使用 **对 OpenFormContainer** 方法或 [MAPIOpenLocalFormContainer](mapiopenlocalformcontainer.md) 函数的调用;不能使用 [IMAPIFormMgr：：SelectFormContainer](imapiformmgr-selectformcontainer.md) 方法使用户可以选择本地表单容器。</span><span class="sxs-lookup"><span data-stu-id="c7634-134">To open the local form container, you must use a call to **OpenFormContainer** method or the [MAPIOpenLocalFormContainer](mapiopenlocalformcontainer.md) function; you cannot use the [IMAPIFormMgr::SelectFormContainer](imapiformmgr-selectformcontainer.md) method to enable the user to select the local form container.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="c7634-135">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="c7634-135">MFCMAPI reference</span></span>

<span data-ttu-id="c7634-136">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c7634-136">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c7634-137">**文件**</span><span class="sxs-lookup"><span data-stu-id="c7634-137">**File**</span></span>|<span data-ttu-id="c7634-138">**函数**</span><span class="sxs-lookup"><span data-stu-id="c7634-138">**Function**</span></span>|<span data-ttu-id="c7634-139">**备注**</span><span class="sxs-lookup"><span data-stu-id="c7634-139">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c7634-140">MainDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="c7634-140">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="c7634-141">CMainDlg：：OnOpenFormContainer</span><span class="sxs-lookup"><span data-stu-id="c7634-141">CMainDlg::OnOpenFormContainer</span></span>  <br/> |<span data-ttu-id="c7634-142">MFCMAPI 使用 **IMAPIFormMgr：：OpenFormContainer** 方法来检索表单容器，以便可以呈现容器的内容。</span><span class="sxs-lookup"><span data-stu-id="c7634-142">MFCMAPI uses the **IMAPIFormMgr::OpenFormContainer** method to retrieve a form container so the container's contents can be rendered.</span></span>  <br/> |
|<span data-ttu-id="c7634-143">MsgStoreDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="c7634-143">MsgStoreDlg.cpp</span></span>  <br/> |<span data-ttu-id="c7634-144">CMsgStoreDlg：：OnOpenFormContainer</span><span class="sxs-lookup"><span data-stu-id="c7634-144">CMsgStoreDlg::OnOpenFormContainer</span></span>  <br/> |<span data-ttu-id="c7634-145">MFCMAPI 使用 **IMAPIFormMgr：：OpenFormContainer** 方法检索文件夹的表单容器，以便可以呈现容器的内容。</span><span class="sxs-lookup"><span data-stu-id="c7634-145">MFCMAPI uses the **IMAPIFormMgr::OpenFormContainer** method to retrieve a form container for a folder so the container's contents can be rendered.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c7634-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7634-146">See also</span></span>



[<span data-ttu-id="c7634-147">IMAPIFormContainer::InstallForm</span><span class="sxs-lookup"><span data-stu-id="c7634-147">IMAPIFormContainer::InstallForm</span></span>](imapiformcontainer-installform.md)
  
[<span data-ttu-id="c7634-148">IMAPIFormMgr::SelectFormContainer</span><span class="sxs-lookup"><span data-stu-id="c7634-148">IMAPIFormMgr::SelectFormContainer</span></span>](imapiformmgr-selectformcontainer.md)
  
[<span data-ttu-id="c7634-149">MAPIOpenLocalFormContainer</span><span class="sxs-lookup"><span data-stu-id="c7634-149">MAPIOpenLocalFormContainer</span></span>](mapiopenlocalformcontainer.md)
  
[<span data-ttu-id="c7634-150">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c7634-150">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)


[<span data-ttu-id="c7634-151">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="c7634-151">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

