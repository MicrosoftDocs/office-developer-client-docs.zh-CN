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
# <a name="imapiformcontainerinstallform"></a><span data-ttu-id="9e0a0-103">IMAPIFormContainer::InstallForm</span><span class="sxs-lookup"><span data-stu-id="9e0a0-103">IMAPIFormContainer::InstallForm</span></span>

  
  
<span data-ttu-id="9e0a0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9e0a0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9e0a0-105">将表单安装到表单库中。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-105">Installs a form into a form library.</span></span>
  
```cpp
HRESULT InstallForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPCSTR szCfgPathName
);
```

## <a name="parameters"></a><span data-ttu-id="9e0a0-106">参数</span><span class="sxs-lookup"><span data-stu-id="9e0a0-106">Parameters</span></span>

 <span data-ttu-id="9e0a0-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="9e0a0-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="9e0a0-108">实时此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-108">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span> <span data-ttu-id="9e0a0-109">除非客户端应用程序在_ulFlags_参数中设置了 MAPI_DIALOG 标志, 否则将忽略_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-109">The  _ulUIParam_ parameter is ignored unless the client application sets the MAPI_DIALOG flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="9e0a0-110">如果不同时传递 MAPI_DIALOG, 则_ulUIParam_参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-110">The  _ulUIParam_ parameter can be NULL if MAPI_DIALOG is not also passed.</span></span> 
    
 <span data-ttu-id="9e0a0-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="9e0a0-111">_ulFlags_</span></span>
  
> <span data-ttu-id="9e0a0-112">实时用于控制表单安装的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-112">[in] A bitmask of flags that controls the installation of the form.</span></span> <span data-ttu-id="9e0a0-113">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="9e0a0-113">The following flags can be set:</span></span>
    
<span data-ttu-id="9e0a0-114">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="9e0a0-114">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="9e0a0-115">显示一个对话框, 以提供进度信息或提示用户详细信息。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-115">Displays a dialog box to provide progress information or prompt the user for more information.</span></span> <span data-ttu-id="9e0a0-116">如果未设置此标志, 则不会显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-116">If this flag is not set, no dialog box is displayed.</span></span>
    
<span data-ttu-id="9e0a0-117">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="9e0a0-117">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="9e0a0-118">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-118">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="9e0a0-119">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-119">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
<span data-ttu-id="9e0a0-120">MAPIFORM_INSTALL_OVERWRITEONCONFLICT</span><span class="sxs-lookup"><span data-stu-id="9e0a0-120">MAPIFORM_INSTALL_OVERWRITEONCONFLICT</span></span> 
  
> <span data-ttu-id="9e0a0-121">如果已存在另一个处理此表单处理的邮件类的窗体, 请将现有表单替换为此表单。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-121">If another form already exists that handles the message class handled by this form, replace the existing form with this one.</span></span> <span data-ttu-id="9e0a0-122">如果还存在 MAPI_DIALOG 标志, 则忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-122">This flag is ignored if the MAPI_DIALOG flag is also present.</span></span> 
    
 <span data-ttu-id="9e0a0-123">_szCfgPathName_</span><span class="sxs-lookup"><span data-stu-id="9e0a0-123">_szCfgPathName_</span></span>
  
> <span data-ttu-id="9e0a0-124">实时表单的配置文件的路径。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-124">[in] The path to the form's configuration file.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9e0a0-125">返回值</span><span class="sxs-lookup"><span data-stu-id="9e0a0-125">Return value</span></span>

<span data-ttu-id="9e0a0-126">S_OK</span><span class="sxs-lookup"><span data-stu-id="9e0a0-126">S_OK</span></span> 
  
> <span data-ttu-id="9e0a0-127">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-127">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="9e0a0-128">MAPI_E_EXTENDED_ERROR</span><span class="sxs-lookup"><span data-stu-id="9e0a0-128">MAPI_E_EXTENDED_ERROR</span></span> 
  
> <span data-ttu-id="9e0a0-129">发生了实现错误。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-129">An implementation error occurred.</span></span> <span data-ttu-id="9e0a0-130">若要获取与错误相关联的[MAPIERROR](mapierror.md)结构, 请调用[IMAPIFormContainer:: GetLastError](imapiformcontainer-getlasterror.md)方法。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-130">To get the [MAPIERROR](mapierror.md) structure that is associated with the error, call the [IMAPIFormContainer::GetLastError](imapiformcontainer-getlasterror.md) method.</span></span> 
    
<span data-ttu-id="9e0a0-131">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="9e0a0-131">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="9e0a0-132">用户取消了窗体的安装, 通常通过单击对话框中的 "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-132">The user canceled the installation of the form, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="notes-to-implementers"></a><span data-ttu-id="9e0a0-133">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="9e0a0-133">Notes to implementers</span></span>

<span data-ttu-id="9e0a0-134">表单库提供程序应填写**MAPIERROR**结构, 如果出现以下任一情况, 则返回 MAPI_E_EXTENDED_ERROR:</span><span class="sxs-lookup"><span data-stu-id="9e0a0-134">Form library providers should fill in a **MAPIERROR** structure and return MAPI_E_EXTENDED_ERROR if any of the following conditions occur:</span></span> 
  
- <span data-ttu-id="9e0a0-135">找不到配置文件。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-135">The configuration file is not found.</span></span>
    
- <span data-ttu-id="9e0a0-136">配置文件不可读。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-136">The configuration file is not readable.</span></span>
    
- <span data-ttu-id="9e0a0-137">配置文件无效。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-137">The configuration file is invalid.</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="9e0a0-138">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="9e0a0-138">Notes to callers</span></span>

<span data-ttu-id="9e0a0-139">客户端应用程序调用**IMAPIFormContainer:: InstallForm**方法将表单安装到特定的表单容器中。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-139">Client applications call the **IMAPIFormContainer::InstallForm** method to install a form into a specific form container.</span></span> <span data-ttu-id="9e0a0-140">_szCfgPathName_参数必须包含表单配置文件的路径 (即, 具有用于描述表单及其实现的扩展名为. cfg 的文件)。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-140">The  _szCfgPathName_ parameter must contain the path of a form configuration file (that is, a file with the .cfg extension that describes the form and its implementation).</span></span> <span data-ttu-id="9e0a0-141">_ulFlags_参数中的标志指定以下内容:</span><span class="sxs-lookup"><span data-stu-id="9e0a0-141">The flags in the  _ulFlags_ parameter specify the following:</span></span> 
  
- <span data-ttu-id="9e0a0-142">如果设置了 MAPI_DIALOG 标志, 则显示一个用户界面, 使正在安装该表单的用户可以指定安装详细信息。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-142">If the MAPI_DIALOG flag is set, a user interface is displayed, enabling the user who is installing the form to specify installation details.</span></span>
    
- <span data-ttu-id="9e0a0-143">如果设置了 MAPIFORM_INSTALL_OVERWRITEONCONFLICT 标志, 则同一邮件类的任何以前的窗体将替换为正在安装的窗体。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-143">If the MAPIFORM_INSTALL_OVERWRITEONCONFLICT flag is set, any previous form for the same message class is replaced with the form being installed.</span></span> <span data-ttu-id="9e0a0-144">否则, 将使用当前的表单说明 (如果存在) 合并表单安装。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-144">Otherwise, the form installation is merged with the current form description, if one exists.</span></span>
    
- <span data-ttu-id="9e0a0-145">如果设置了 MAPI_DIALOG, 则将忽略 MAPIFORM_INSTALL_OVERWRITEONCONFLICT。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-145">If MAPI_DIALOG is set, MAPIFORM_INSTALL_OVERWRITEONCONFLICT is ignored.</span></span>
    
- <span data-ttu-id="9e0a0-146">标记集中缺少 MAPIFORM_INSTALL_OVERWRITEONCONFLICT 意味着将完成合并。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-146">The absence of MAPIFORM_INSTALL_OVERWRITEONCONFLICT in the flag set means that a merge will be done.</span></span> <span data-ttu-id="9e0a0-147">将会安装在表单说明中当前未出现的 cfg 文件中的任何新平台, 并且不会进行其他更改。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-147">Any new platforms in the .cfg file that are not currently present in the form description will be installed and no other changes will occur.</span></span>
    
- <span data-ttu-id="9e0a0-148">如果设置了 MAPI_UNICODE 标志, 则表单配置文件的路径为 UNICODE 字符串。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-148">If the MAPI_UNICODE flag is set, the path of the form configuration file is a Unicode string.</span></span> 
    
<span data-ttu-id="9e0a0-149">客户端应调用[IMAPIFormContainer:: GetLastError](imapiformcontainer-getlasterror.md) (如果**InstallForm**返回 MAPI_E_EXTENDED_ERROR), 并应检查返回的[MAPIERROR](mapierror.md)结构以确定引发错误的条件。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-149">Clients should call [IMAPIFormContainer::GetLastError](imapiformcontainer-getlasterror.md) if **InstallForm** returns MAPI_E_EXTENDED_ERROR, and they should check the returned [MAPIERROR](mapierror.md) structure to determine the condition that raised the error.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="9e0a0-150">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="9e0a0-150">MFCMAPI reference</span></span>

<span data-ttu-id="9e0a0-151">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-151">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="9e0a0-152">**文件**</span><span class="sxs-lookup"><span data-stu-id="9e0a0-152">**File**</span></span>|<span data-ttu-id="9e0a0-153">**函数**</span><span class="sxs-lookup"><span data-stu-id="9e0a0-153">**Function**</span></span>|<span data-ttu-id="9e0a0-154">**备注**</span><span class="sxs-lookup"><span data-stu-id="9e0a0-154">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9e0a0-155">FormContainerDlg</span><span class="sxs-lookup"><span data-stu-id="9e0a0-155">FormContainerDlg.cpp</span></span>  <br/> |<span data-ttu-id="9e0a0-156">CFormContainerDlg:: OnInstallForm</span><span class="sxs-lookup"><span data-stu-id="9e0a0-156">CFormContainerDlg::OnInstallForm</span></span>  <br/> |<span data-ttu-id="9e0a0-157">MFCMAPI 使用**IMAPIFormContainer:: InstallForm**方法在表单容器中安装表单。</span><span class="sxs-lookup"><span data-stu-id="9e0a0-157">MFCMAPI uses the **IMAPIFormContainer::InstallForm** method to install a form in a form container.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9e0a0-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e0a0-158">See also</span></span>



[<span data-ttu-id="9e0a0-159">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="9e0a0-159">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="9e0a0-160">IMAPIFormContainer : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9e0a0-160">IMAPIFormContainer : IUnknown</span></span>](imapiformcontaineriunknown.md)


[<span data-ttu-id="9e0a0-161">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="9e0a0-161">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

