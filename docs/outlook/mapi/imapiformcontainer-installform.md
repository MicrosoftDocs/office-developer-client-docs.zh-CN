---
title: IMAPIFormContainerInstallForm
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormContainer.InstallForm
api_type:
- COM
ms.assetid: b39ca52c-4dbe-41c0-9e1b-3998a9dc9742
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a0650033e4fea79046eac5757e3d0deb963c38e6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405084"
---
# <a name="imapiformcontainerinstallform"></a><span data-ttu-id="34538-103">IMAPIFormContainer::InstallForm</span><span class="sxs-lookup"><span data-stu-id="34538-103">IMAPIFormContainer::InstallForm</span></span>

  
  
<span data-ttu-id="34538-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="34538-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="34538-105">将表单安装到表单库中。</span><span class="sxs-lookup"><span data-stu-id="34538-105">Installs a form into a form library.</span></span>
  
```cpp
HRESULT InstallForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPCSTR szCfgPathName
);
```

## <a name="parameters"></a><span data-ttu-id="34538-106">参数</span><span class="sxs-lookup"><span data-stu-id="34538-106">Parameters</span></span>

 <span data-ttu-id="34538-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="34538-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="34538-108">[in]该方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="34538-108">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span> <span data-ttu-id="34538-109">除非  _客户端应用程序在 ulFlags_ 参数中设置 MAPI_DIALOG 标志，否则将忽略  _ulUIParam_ 参数。</span><span class="sxs-lookup"><span data-stu-id="34538-109">The  _ulUIParam_ parameter is ignored unless the client application sets the MAPI_DIALOG flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="34538-110">如果未  _传递 ulUIParam_ 参数，MAPI_DIALOG为 NULL。</span><span class="sxs-lookup"><span data-stu-id="34538-110">The  _ulUIParam_ parameter can be NULL if MAPI_DIALOG is not also passed.</span></span> 
    
 <span data-ttu-id="34538-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="34538-111">_ulFlags_</span></span>
  
> <span data-ttu-id="34538-112">[in]控制表单安装的位掩码标志。</span><span class="sxs-lookup"><span data-stu-id="34538-112">[in] A bitmask of flags that controls the installation of the form.</span></span> <span data-ttu-id="34538-113">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="34538-113">The following flags can be set:</span></span>
    
<span data-ttu-id="34538-114">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="34538-114">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="34538-115">显示一个对话框以提供进度信息或提示用户输入详细信息。</span><span class="sxs-lookup"><span data-stu-id="34538-115">Displays a dialog box to provide progress information or prompt the user for more information.</span></span> <span data-ttu-id="34538-116">如果未设置此标志，则不显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="34538-116">If this flag is not set, no dialog box is displayed.</span></span>
    
<span data-ttu-id="34538-117">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="34538-117">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="34538-118">传入字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="34538-118">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="34538-119">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="34538-119">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
<span data-ttu-id="34538-120">MAPIFORM_INSTALL_OVERWRITEONCONFLICT</span><span class="sxs-lookup"><span data-stu-id="34538-120">MAPIFORM_INSTALL_OVERWRITEONCONFLICT</span></span> 
  
> <span data-ttu-id="34538-121">如果已存在另一个处理此表单处理的邮件类的表单，请将现有表单替换为此表单。</span><span class="sxs-lookup"><span data-stu-id="34538-121">If another form already exists that handles the message class handled by this form, replace the existing form with this one.</span></span> <span data-ttu-id="34538-122">如果还显示"MAPI_DIALOG，则忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="34538-122">This flag is ignored if the MAPI_DIALOG flag is also present.</span></span> 
    
 <span data-ttu-id="34538-123">_szCfgPathName_</span><span class="sxs-lookup"><span data-stu-id="34538-123">_szCfgPathName_</span></span>
  
> <span data-ttu-id="34538-124">[in]表单配置文件的路径。</span><span class="sxs-lookup"><span data-stu-id="34538-124">[in] The path to the form's configuration file.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="34538-125">返回值</span><span class="sxs-lookup"><span data-stu-id="34538-125">Return value</span></span>

<span data-ttu-id="34538-126">S_OK</span><span class="sxs-lookup"><span data-stu-id="34538-126">S_OK</span></span> 
  
> <span data-ttu-id="34538-127">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="34538-127">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="34538-128">MAPI_E_EXTENDED_ERROR</span><span class="sxs-lookup"><span data-stu-id="34538-128">MAPI_E_EXTENDED_ERROR</span></span> 
  
> <span data-ttu-id="34538-129">发生实现错误。</span><span class="sxs-lookup"><span data-stu-id="34538-129">An implementation error occurred.</span></span> <span data-ttu-id="34538-130">若要获取与 [错误关联的 MAPIERROR](mapierror.md) 结构，请调用 [IMAPIFormContainer：：GetLastError](imapiformcontainer-getlasterror.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="34538-130">To get the [MAPIERROR](mapierror.md) structure that is associated with the error, call the [IMAPIFormContainer::GetLastError](imapiformcontainer-getlasterror.md) method.</span></span> 
    
<span data-ttu-id="34538-131">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="34538-131">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="34538-132">用户通常通过单击对话框中的"取消"按钮来取消窗体的安装。</span><span class="sxs-lookup"><span data-stu-id="34538-132">The user canceled the installation of the form, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="notes-to-implementers"></a><span data-ttu-id="34538-133">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="34538-133">Notes to implementers</span></span>

<span data-ttu-id="34538-134">表单库提供程序应填写 **MAPIERROR** 结构，并MAPI_E_EXTENDED_ERROR出现以下任一情况时返回一个表单库：</span><span class="sxs-lookup"><span data-stu-id="34538-134">Form library providers should fill in a **MAPIERROR** structure and return MAPI_E_EXTENDED_ERROR if any of the following conditions occur:</span></span> 
  
- <span data-ttu-id="34538-135">找不到配置文件。</span><span class="sxs-lookup"><span data-stu-id="34538-135">The configuration file is not found.</span></span>
    
- <span data-ttu-id="34538-136">配置文件不可读。</span><span class="sxs-lookup"><span data-stu-id="34538-136">The configuration file is not readable.</span></span>
    
- <span data-ttu-id="34538-137">配置文件无效。</span><span class="sxs-lookup"><span data-stu-id="34538-137">The configuration file is invalid.</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="34538-138">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="34538-138">Notes to callers</span></span>

<span data-ttu-id="34538-139">客户端应用程序调用 **IMAPIFormContainer：：InstallForm** 方法将表单安装到特定的表单容器中。</span><span class="sxs-lookup"><span data-stu-id="34538-139">Client applications call the **IMAPIFormContainer::InstallForm** method to install a form into a specific form container.</span></span> <span data-ttu-id="34538-140">_szCfgPathName_ 参数必须包含表单配置文件的路径 (即具有 .cfg 扩展名的文件，该文件描述表单及其实现) 。</span><span class="sxs-lookup"><span data-stu-id="34538-140">The  _szCfgPathName_ parameter must contain the path of a form configuration file (that is, a file with the .cfg extension that describes the form and its implementation).</span></span> <span data-ttu-id="34538-141">_ulFlags_ 参数中的标志指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="34538-141">The flags in the  _ulFlags_ parameter specify the following:</span></span> 
  
- <span data-ttu-id="34538-142">如果MAPI_DIALOG，将显示用户界面，使安装表单的用户能够指定安装详细信息。</span><span class="sxs-lookup"><span data-stu-id="34538-142">If the MAPI_DIALOG flag is set, a user interface is displayed, enabling the user who is installing the form to specify installation details.</span></span>
    
- <span data-ttu-id="34538-143">如果MAPIFORM_INSTALL_OVERWRITEONCONFLICT，则同一邮件类之前的任何窗体都将被替换为正在安装的窗体。</span><span class="sxs-lookup"><span data-stu-id="34538-143">If the MAPIFORM_INSTALL_OVERWRITEONCONFLICT flag is set, any previous form for the same message class is replaced with the form being installed.</span></span> <span data-ttu-id="34538-144">否则，表单安装将与当前表单说明（如果存在）合并。</span><span class="sxs-lookup"><span data-stu-id="34538-144">Otherwise, the form installation is merged with the current form description, if one exists.</span></span>
    
- <span data-ttu-id="34538-145">如果MAPI_DIALOG，MAPIFORM_INSTALL_OVERWRITEONCONFLICT忽略。</span><span class="sxs-lookup"><span data-stu-id="34538-145">If MAPI_DIALOG is set, MAPIFORM_INSTALL_OVERWRITEONCONFLICT is ignored.</span></span>
    
- <span data-ttu-id="34538-146">标志集MAPIFORM_INSTALL_OVERWRITEONCONFLICT，意味着将完成合并。</span><span class="sxs-lookup"><span data-stu-id="34538-146">The absence of MAPIFORM_INSTALL_OVERWRITEONCONFLICT in the flag set means that a merge will be done.</span></span> <span data-ttu-id="34538-147">将安装表单说明中当前不存在的 .cfg 文件中的任何新平台，并且不会发生其他更改。</span><span class="sxs-lookup"><span data-stu-id="34538-147">Any new platforms in the .cfg file that are not currently present in the form description will be installed and no other changes will occur.</span></span>
    
- <span data-ttu-id="34538-148">如果MAPI_UNICODE，则表单配置文件的路径为 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="34538-148">If the MAPI_UNICODE flag is set, the path of the form configuration file is a Unicode string.</span></span> 
    
<span data-ttu-id="34538-149">如果 **InstallForm** 返回 MAPI_E_EXTENDED_ERROR，客户端应调用 [IMAPIFormContainer：：GetLastError，](imapiformcontainer-getlasterror.md)并且应检查返回的 [MAPIERROR](mapierror.md)结构以确定引发错误的条件。</span><span class="sxs-lookup"><span data-stu-id="34538-149">Clients should call [IMAPIFormContainer::GetLastError](imapiformcontainer-getlasterror.md) if **InstallForm** returns MAPI_E_EXTENDED_ERROR, and they should check the returned [MAPIERROR](mapierror.md) structure to determine the condition that raised the error.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="34538-150">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="34538-150">MFCMAPI reference</span></span>

<span data-ttu-id="34538-151">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="34538-151">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="34538-152">**文件**</span><span class="sxs-lookup"><span data-stu-id="34538-152">**File**</span></span>|<span data-ttu-id="34538-153">**函数**</span><span class="sxs-lookup"><span data-stu-id="34538-153">**Function**</span></span>|<span data-ttu-id="34538-154">**备注**</span><span class="sxs-lookup"><span data-stu-id="34538-154">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="34538-155">FormContainerDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="34538-155">FormContainerDlg.cpp</span></span>  <br/> |<span data-ttu-id="34538-156">CFormContainerDlg：：OnInstallForm</span><span class="sxs-lookup"><span data-stu-id="34538-156">CFormContainerDlg::OnInstallForm</span></span>  <br/> |<span data-ttu-id="34538-157">MFCMAPI 使用 **IMAPIFormContainer：：InstallForm** 方法在表单容器中安装表单。</span><span class="sxs-lookup"><span data-stu-id="34538-157">MFCMAPI uses the **IMAPIFormContainer::InstallForm** method to install a form in a form container.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="34538-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34538-158">See also</span></span>



[<span data-ttu-id="34538-159">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="34538-159">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="34538-160">IMAPIFormContainer : IUnknown</span><span class="sxs-lookup"><span data-stu-id="34538-160">IMAPIFormContainer : IUnknown</span></span>](imapiformcontaineriunknown.md)


[<span data-ttu-id="34538-161">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="34538-161">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

