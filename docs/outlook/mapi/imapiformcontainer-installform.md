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
ms.openlocfilehash: fd7bc8f051e9584fc63f22bdbaf9696c2e4d15a3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580934"
---
# <a name="imapiformcontainerinstallform"></a><span data-ttu-id="5bed4-103">IMAPIFormContainer::InstallForm</span><span class="sxs-lookup"><span data-stu-id="5bed4-103">IMAPIFormContainer::InstallForm</span></span>

  
  
<span data-ttu-id="5bed4-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5bed4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5bed4-105">将窗体安装到表单库。</span><span class="sxs-lookup"><span data-stu-id="5bed4-105">Installs a form into a form library.</span></span>
  
```cpp
HRESULT InstallForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPCSTR szCfgPathName
);
```

## <a name="parameters"></a><span data-ttu-id="5bed4-106">参数</span><span class="sxs-lookup"><span data-stu-id="5bed4-106">Parameters</span></span>

 <span data-ttu-id="5bed4-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="5bed4-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="5bed4-108">[in]任何对话框的父窗口或该方法显示的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="5bed4-108">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span> <span data-ttu-id="5bed4-109">除非客户端应用程序中的_ulFlags_参数设置 MAPI_DIALOG 标志，则将忽略该_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="5bed4-109">The  _ulUIParam_ parameter is ignored unless the client application sets the MAPI_DIALOG flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="5bed4-110">如果还未传递 MAPI_DIALOG _ulUIParam_参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="5bed4-110">The  _ulUIParam_ parameter can be NULL if MAPI_DIALOG is not also passed.</span></span> 
    
 <span data-ttu-id="5bed4-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5bed4-111">_ulFlags_</span></span>
  
> <span data-ttu-id="5bed4-112">[in]位掩码的标志的控件的窗体的安装。</span><span class="sxs-lookup"><span data-stu-id="5bed4-112">[in] A bitmask of flags that controls the installation of the form.</span></span> <span data-ttu-id="5bed4-113">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="5bed4-113">The following flags can be set:</span></span>
    
<span data-ttu-id="5bed4-114">MAPI_DIALOG</span><span class="sxs-lookup"><span data-stu-id="5bed4-114">MAPI_DIALOG</span></span> 
  
> <span data-ttu-id="5bed4-115">显示一个对话框，以提供进度信息或提示用户输入的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5bed4-115">Displays a dialog box to provide progress information or prompt the user for more information.</span></span> <span data-ttu-id="5bed4-116">如果未设置此标志，则不显示任何对话框。</span><span class="sxs-lookup"><span data-stu-id="5bed4-116">If this flag is not set, no dialog box is displayed.</span></span>
    
<span data-ttu-id="5bed4-117">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5bed4-117">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="5bed4-118">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="5bed4-118">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="5bed4-119">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="5bed4-119">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
<span data-ttu-id="5bed4-120">MAPIFORM_INSTALL_OVERWRITEONCONFLICT</span><span class="sxs-lookup"><span data-stu-id="5bed4-120">MAPIFORM_INSTALL_OVERWRITEONCONFLICT</span></span> 
  
> <span data-ttu-id="5bed4-121">如果另一个窗体已存在的邮件类处理由此窗体的句柄，请使用此替换现有的表单。</span><span class="sxs-lookup"><span data-stu-id="5bed4-121">If another form already exists that handles the message class handled by this form, replace the existing form with this one.</span></span> <span data-ttu-id="5bed4-122">如果 MAPI_DIALOG 标志还存在，则忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="5bed4-122">This flag is ignored if the MAPI_DIALOG flag is also present.</span></span> 
    
 <span data-ttu-id="5bed4-123">_szCfgPathName_</span><span class="sxs-lookup"><span data-stu-id="5bed4-123">_szCfgPathName_</span></span>
  
> <span data-ttu-id="5bed4-124">[in]窗体的配置文件的路径。</span><span class="sxs-lookup"><span data-stu-id="5bed4-124">[in] The path to the form's configuration file.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="5bed4-125">返回值</span><span class="sxs-lookup"><span data-stu-id="5bed4-125">Return value</span></span>

<span data-ttu-id="5bed4-126">S_OK</span><span class="sxs-lookup"><span data-stu-id="5bed4-126">S_OK</span></span> 
  
> <span data-ttu-id="5bed4-127">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="5bed4-127">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="5bed4-128">MAPI_E_EXTENDED_ERROR</span><span class="sxs-lookup"><span data-stu-id="5bed4-128">MAPI_E_EXTENDED_ERROR</span></span> 
  
> <span data-ttu-id="5bed4-129">实现时出错。</span><span class="sxs-lookup"><span data-stu-id="5bed4-129">An implementation error occurred.</span></span> <span data-ttu-id="5bed4-130">要获取与错误关联的[MAPIERROR](mapierror.md)结构，请调用[IMAPIFormContainer::GetLastError](imapiformcontainer-getlasterror.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5bed4-130">To get the [MAPIERROR](mapierror.md) structure that is associated with the error, call the [IMAPIFormContainer::GetLastError](imapiformcontainer-getlasterror.md) method.</span></span> 
    
<span data-ttu-id="5bed4-131">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="5bed4-131">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="5bed4-132">用户取消安装的窗体，通常通过单击对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="5bed4-132">The user canceled the installation of the form, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="notes-to-implementers"></a><span data-ttu-id="5bed4-133">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="5bed4-133">Notes to implementers</span></span>

<span data-ttu-id="5bed4-134">窗体库提供程序应填充**MAPIERROR**结构中，并返回 MAPI_E_EXTENDED_ERROR，如果发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="5bed4-134">Form library providers should fill in a **MAPIERROR** structure and return MAPI_E_EXTENDED_ERROR if any of the following conditions occur:</span></span> 
  
- <span data-ttu-id="5bed4-135">未找到配置文件。</span><span class="sxs-lookup"><span data-stu-id="5bed4-135">The configuration file is not found.</span></span>
    
- <span data-ttu-id="5bed4-136">配置文件不可读。</span><span class="sxs-lookup"><span data-stu-id="5bed4-136">The configuration file is not readable.</span></span>
    
- <span data-ttu-id="5bed4-137">无效的配置文件。</span><span class="sxs-lookup"><span data-stu-id="5bed4-137">The configuration file is invalid.</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="5bed4-138">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="5bed4-138">Notes to callers</span></span>

<span data-ttu-id="5bed4-139">客户端应用程序调用**IMAPIFormContainer::InstallForm**方法以安装到特定的窗体容器的窗体。</span><span class="sxs-lookup"><span data-stu-id="5bed4-139">Client applications call the **IMAPIFormContainer::InstallForm** method to install a form into a specific form container.</span></span> <span data-ttu-id="5bed4-140">_SzCfgPathName_参数必须包含窗体配置文件 （即，介绍了窗体和其实现.cfg 扩展名文件） 的路径。</span><span class="sxs-lookup"><span data-stu-id="5bed4-140">The  _szCfgPathName_ parameter must contain the path of a form configuration file (that is, a file with the .cfg extension that describes the form and its implementation).</span></span> <span data-ttu-id="5bed4-141">Flags _ulFlags_参数中的指定以下设置：</span><span class="sxs-lookup"><span data-stu-id="5bed4-141">The flags in the  _ulFlags_ parameter specify the following:</span></span> 
  
- <span data-ttu-id="5bed4-142">如果设置了 MAPI_DIALOG 标志，将显示用户界面，启用安装时指定安装详细信息窗体的用户。</span><span class="sxs-lookup"><span data-stu-id="5bed4-142">If the MAPI_DIALOG flag is set, a user interface is displayed, enabling the user who is installing the form to specify installation details.</span></span>
    
- <span data-ttu-id="5bed4-143">如果设置了 MAPIFORM_INSTALL_OVERWRITEONCONFLICT 标志，与正在安装该表单替换同一邮件类的任何以前窗体。</span><span class="sxs-lookup"><span data-stu-id="5bed4-143">If the MAPIFORM_INSTALL_OVERWRITEONCONFLICT flag is set, any previous form for the same message class is replaced with the form being installed.</span></span> <span data-ttu-id="5bed4-144">否则，窗体安装合并与当前的窗体说明中，如果存在。</span><span class="sxs-lookup"><span data-stu-id="5bed4-144">Otherwise, the form installation is merged with the current form description, if one exists.</span></span>
    
- <span data-ttu-id="5bed4-145">如果设置 MAPI_DIALOG，则忽略 MAPIFORM_INSTALL_OVERWRITEONCONFLICT。</span><span class="sxs-lookup"><span data-stu-id="5bed4-145">If MAPI_DIALOG is set, MAPIFORM_INSTALL_OVERWRITEONCONFLICT is ignored.</span></span>
    
- <span data-ttu-id="5bed4-146">在标记不存在 MAPIFORM_INSTALL_OVERWRITEONCONFLICT 设置意味着将完成合并。</span><span class="sxs-lookup"><span data-stu-id="5bed4-146">The absence of MAPIFORM_INSTALL_OVERWRITEONCONFLICT in the flag set means that a merge will be done.</span></span> <span data-ttu-id="5bed4-147">将安装任何新平台.cfg 文件中的，不窗体说明中当前存在和任何其他更改，则会发生。</span><span class="sxs-lookup"><span data-stu-id="5bed4-147">Any new platforms in the .cfg file that are not currently present in the form description will be installed and no other changes will occur.</span></span>
    
- <span data-ttu-id="5bed4-148">如果设置了 MAPI_UNICODE 标志，窗体配置文件的路径为 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="5bed4-148">If the MAPI_UNICODE flag is set, the path of the form configuration file is a Unicode string.</span></span> 
    
<span data-ttu-id="5bed4-149">如果**InstallForm**返回 MAPI_E_EXTENDED_ERROR，并且他们应检查返回的[MAPIERROR](mapierror.md)结构，以确定引发错误条件，客户端应调用[IMAPIFormContainer::GetLastError](imapiformcontainer-getlasterror.md) 。</span><span class="sxs-lookup"><span data-stu-id="5bed4-149">Clients should call [IMAPIFormContainer::GetLastError](imapiformcontainer-getlasterror.md) if **InstallForm** returns MAPI_E_EXTENDED_ERROR, and they should check the returned [MAPIERROR](mapierror.md) structure to determine the condition that raised the error.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="5bed4-150">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="5bed4-150">MFCMAPI reference</span></span>

<span data-ttu-id="5bed4-151">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="5bed4-151">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="5bed4-152">**文件**</span><span class="sxs-lookup"><span data-stu-id="5bed4-152">**File**</span></span>|<span data-ttu-id="5bed4-153">**函数**</span><span class="sxs-lookup"><span data-stu-id="5bed4-153">**Function**</span></span>|<span data-ttu-id="5bed4-154">**Comment**</span><span class="sxs-lookup"><span data-stu-id="5bed4-154">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5bed4-155">FormContainerDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="5bed4-155">FormContainerDlg.cpp</span></span>  <br/> |<span data-ttu-id="5bed4-156">CFormContainerDlg::OnInstallForm</span><span class="sxs-lookup"><span data-stu-id="5bed4-156">CFormContainerDlg::OnInstallForm</span></span>  <br/> |<span data-ttu-id="5bed4-157">MFCMAPI 使用**IMAPIFormContainer::InstallForm**方法在窗体容器中安装窗体。</span><span class="sxs-lookup"><span data-stu-id="5bed4-157">MFCMAPI uses the **IMAPIFormContainer::InstallForm** method to install a form in a form container.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5bed4-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5bed4-158">See also</span></span>



[<span data-ttu-id="5bed4-159">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="5bed4-159">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="5bed4-160">IMAPIFormContainer : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5bed4-160">IMAPIFormContainer : IUnknown</span></span>](imapiformcontaineriunknown.md)


[<span data-ttu-id="5bed4-161">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="5bed4-161">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

