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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393115"
---
# <a name="imapiformmgropenformcontainer"></a><span data-ttu-id="f3c5a-103">IMAPIFormMgr::OpenFormContainer</span><span class="sxs-lookup"><span data-stu-id="f3c5a-103">IMAPIFormMgr::OpenFormContainer</span></span>

  
  
<span data-ttu-id="f3c5a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f3c5a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f3c5a-105">打开特定窗体容器[IMAPIFormContainer](imapiformcontaineriunknown.md)界面。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-105">Opens an [IMAPIFormContainer](imapiformcontaineriunknown.md) interface for a specific form container.</span></span> 
  
```cpp
HRESULT OpenFormContainer(
  HFRMREG hfrmreg,
  LPUNKNOWN lpunk,
  LPMAPIFORMCONTAINER FAR * lppfcnt
);
```

## <a name="parameters"></a><span data-ttu-id="f3c5a-106">参数</span><span class="sxs-lookup"><span data-stu-id="f3c5a-106">Parameters</span></span>

 <span data-ttu-id="f3c5a-107">_hfrmreg_</span><span class="sxs-lookup"><span data-stu-id="f3c5a-107">_hfrmreg_</span></span>
  
> <span data-ttu-id="f3c5a-108">[in]HFRMREG 枚举指示要打开的窗体库 （也就是说，表单容器来打开）。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-108">[in] An HFRMREG enumeration that indicates the form library to open (that is, the form container to open).</span></span> <span data-ttu-id="f3c5a-109">HFRMREG 枚举是特定于窗体库提供程序的枚举。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-109">An HFRMREG enumeration is an enumeration that is specific to a form library provider.</span></span> <span data-ttu-id="f3c5a-110">可能 HFRMREG 值包括：</span><span class="sxs-lookup"><span data-stu-id="f3c5a-110">Possible HFRMREG values include the following:</span></span>
    
<span data-ttu-id="f3c5a-111">HFRMREG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="f3c5a-111">HFRMREG_DEFAULT</span></span> 
  
> <span data-ttu-id="f3c5a-112">一种方便的窗体容器。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-112">A convenient form container.</span></span>
    
<span data-ttu-id="f3c5a-113">HFRMREG_FOLDER</span><span class="sxs-lookup"><span data-stu-id="f3c5a-113">HFRMREG_FOLDER</span></span> 
  
> <span data-ttu-id="f3c5a-114">文件夹的容器。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-114">A folder container.</span></span> 
    
<span data-ttu-id="f3c5a-115">HFRMREG_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="f3c5a-115">HFRMREG_PERSONAL</span></span> 
  
> <span data-ttu-id="f3c5a-116">默认的邮件存储的容器。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-116">The container for the default message store.</span></span> 
    
<span data-ttu-id="f3c5a-117">HFRMREG_LOCAL</span><span class="sxs-lookup"><span data-stu-id="f3c5a-117">HFRMREG_LOCAL</span></span> 
  
> <span data-ttu-id="f3c5a-118">本地窗体的容器。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-118">A local form container.</span></span> 
    
 <span data-ttu-id="f3c5a-119">_lpunk_</span><span class="sxs-lookup"><span data-stu-id="f3c5a-119">_lpunk_</span></span>
  
> <span data-ttu-id="f3c5a-120">[in]指向为其打开接口的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-120">[in] A pointer to the object for which the interface is opened.</span></span> <span data-ttu-id="f3c5a-121">_Lpunk_参数必须为**空**，除非_hfrmreg_参数的值需要对象指针。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-121">The  _lpunk_ parameter must be **null** unless the value for the  _hfrmreg_ parameter requires an object pointer.</span></span> 
    
 <span data-ttu-id="f3c5a-122">_lppfcnt_</span><span class="sxs-lookup"><span data-stu-id="f3c5a-122">_lppfcnt_</span></span>
  
> <span data-ttu-id="f3c5a-123">[输出]指向返回窗体容器对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-123">[out] A pointer to a pointer to the returned form container object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f3c5a-124">返回值</span><span class="sxs-lookup"><span data-stu-id="f3c5a-124">Return value</span></span>

<span data-ttu-id="f3c5a-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="f3c5a-125">S_OK</span></span> 
  
> <span data-ttu-id="f3c5a-126">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-126">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="f3c5a-127">MAPI_E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="f3c5a-127">MAPI_E_NO_INTERFACE</span></span> 
  
> <span data-ttu-id="f3c5a-128">指向_lpunk_对象不支持所需的接口。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-128">The object pointed to by  _lpunk_ does not support the required interface.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="f3c5a-129">说明</span><span class="sxs-lookup"><span data-stu-id="f3c5a-129">Remarks</span></span>

<span data-ttu-id="f3c5a-130">表单查看器调用**IMAPIFormMgr::OpenFormContainer**方法打开特定窗体容器**IMAPIFormContainer**接口。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-130">Form viewers call the **IMAPIFormMgr::OpenFormContainer** method to open an **IMAPIFormContainer** interface for a specific form container.</span></span> <span data-ttu-id="f3c5a-131">此接口然后可用于安装窗体插入和移除表单从窗体容器。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-131">This interface can then be used for installing forms into and removing forms from a form container.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="f3c5a-132">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="f3c5a-132">Notes to callers</span></span>

<span data-ttu-id="f3c5a-133">如果_hfrmreg_中的值，HFRMREG_FOLDER _lpunk_中使用该接口的标识符必须非**null** ，并且必须允许[IMAPIFolder](imapifolderimapicontainer.md)接口[IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)方法调用。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-133">If the value in  _hfrmreg_ is HFRMREG_FOLDER, the interface identifier used in  _lpunk_ must be non- **null** and must allow [IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) method calls to an [IMAPIFolder](imapifolderimapicontainer.md) interface.</span></span> 
  
<span data-ttu-id="f3c5a-134">若要打开本地窗体容器，必须使用调用**OpenFormContainer**方法或[MAPIOpenLocalFormContainer](mapiopenlocalformcontainer.md)函数中;不能使用[IMAPIFormMgr::SelectFormContainer](imapiformmgr-selectformcontainer.md)方法以使用户能够选择本地窗体容器。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-134">To open the local form container, you must use a call to **OpenFormContainer** method or the [MAPIOpenLocalFormContainer](mapiopenlocalformcontainer.md) function; you cannot use the [IMAPIFormMgr::SelectFormContainer](imapiformmgr-selectformcontainer.md) method to enable the user to select the local form container.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="f3c5a-135">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="f3c5a-135">MFCMAPI reference</span></span>

<span data-ttu-id="f3c5a-136">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-136">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="f3c5a-137">**文件**</span><span class="sxs-lookup"><span data-stu-id="f3c5a-137">**File**</span></span>|<span data-ttu-id="f3c5a-138">**函数**</span><span class="sxs-lookup"><span data-stu-id="f3c5a-138">**Function**</span></span>|<span data-ttu-id="f3c5a-139">**备注**</span><span class="sxs-lookup"><span data-stu-id="f3c5a-139">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f3c5a-140">MainDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="f3c5a-140">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="f3c5a-141">CMainDlg::OnOpenFormContainer</span><span class="sxs-lookup"><span data-stu-id="f3c5a-141">CMainDlg::OnOpenFormContainer</span></span>  <br/> |<span data-ttu-id="f3c5a-142">MFCMAPI 使用**IMAPIFormMgr::OpenFormContainer**方法检索的窗体容器，因此可以呈现容器的内容。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-142">MFCMAPI uses the **IMAPIFormMgr::OpenFormContainer** method to retrieve a form container so the container's contents can be rendered.</span></span>  <br/> |
|<span data-ttu-id="f3c5a-143">MsgStoreDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="f3c5a-143">MsgStoreDlg.cpp</span></span>  <br/> |<span data-ttu-id="f3c5a-144">CMsgStoreDlg::OnOpenFormContainer</span><span class="sxs-lookup"><span data-stu-id="f3c5a-144">CMsgStoreDlg::OnOpenFormContainer</span></span>  <br/> |<span data-ttu-id="f3c5a-145">MFCMAPI 使用**IMAPIFormMgr::OpenFormContainer**方法检索的文件夹的窗体容器，因此可以呈现容器的内容。</span><span class="sxs-lookup"><span data-stu-id="f3c5a-145">MFCMAPI uses the **IMAPIFormMgr::OpenFormContainer** method to retrieve a form container for a folder so the container's contents can be rendered.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f3c5a-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3c5a-146">See also</span></span>



[<span data-ttu-id="f3c5a-147">IMAPIFormContainer::InstallForm</span><span class="sxs-lookup"><span data-stu-id="f3c5a-147">IMAPIFormContainer::InstallForm</span></span>](imapiformcontainer-installform.md)
  
[<span data-ttu-id="f3c5a-148">IMAPIFormMgr::SelectFormContainer</span><span class="sxs-lookup"><span data-stu-id="f3c5a-148">IMAPIFormMgr::SelectFormContainer</span></span>](imapiformmgr-selectformcontainer.md)
  
[<span data-ttu-id="f3c5a-149">MAPIOpenLocalFormContainer</span><span class="sxs-lookup"><span data-stu-id="f3c5a-149">MAPIOpenLocalFormContainer</span></span>](mapiopenlocalformcontainer.md)
  
[<span data-ttu-id="f3c5a-150">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f3c5a-150">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)


[<span data-ttu-id="f3c5a-151">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="f3c5a-151">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

