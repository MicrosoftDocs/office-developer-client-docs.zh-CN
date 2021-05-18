---
title: 安装清单
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9dfb9b6d-2fb4-45bf-a12f-bd10a799ce29
description: 本主题介绍成功安装 Outlook Social Connector (OSC) 提供程序的先决条件，以及您的提供程序安装程序应完成安装检查以正确工作的先决条件。
ms.openlocfilehash: 8fec8523e57ad2678d02a0c5cbc1ad57340e5267
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286336"
---
# <a name="installation-checklist"></a><span data-ttu-id="0cb67-103">安装清单</span><span class="sxs-lookup"><span data-stu-id="0cb67-103">Installation checklist</span></span>

<span data-ttu-id="0cb67-104">本主题介绍成功安装 Outlook Social Connector (OSC) 提供程序的先决条件，以及您的提供程序安装程序应完成安装检查以正确工作的先决条件。</span><span class="sxs-lookup"><span data-stu-id="0cb67-104">This topic describes prerequisites for successfully installing an Outlook Social Connector (OSC) provider, and the installation checks that your provider installer should complete to work correctly.</span></span>
  
## <a name="installation-overview"></a><span data-ttu-id="0cb67-105">安装概述</span><span class="sxs-lookup"><span data-stu-id="0cb67-105">Installation overview</span></span>

<span data-ttu-id="0cb67-106">只有在存在支持版本的 OSC 提供程序Outlook在客户端计算机上安装和启用 OSC 时，用户才应安装 OSC 提供程序。</span><span class="sxs-lookup"><span data-stu-id="0cb67-106">Users should install OSC providers only if a supporting version of Outlook is present and the OSC is installed and enabled on the client computer.</span></span> <span data-ttu-id="0cb67-107">支持版本的 Outlook 是安装在客户端计算机上的 Office Outlook 2003、Office Outlook 2007、Outlook 2010 和 Outlook 2013 (，对于 Outlook 2010 和 Outlook 2013，则由客户端计算机) 上的即点即用提供。</span><span class="sxs-lookup"><span data-stu-id="0cb67-107">Supporting versions of Outlook are Office Outlook 2003, Office Outlook 2007, Outlook 2010 and Outlook 2013 (installed on the client computer or, in the case of Outlook 2010 and Outlook 2013, delivered by Click-to-Run on the client computer).</span></span> <span data-ttu-id="0cb67-108">为了确保成功安装，提供程序安装程序应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0cb67-108">To ensure a successful installation, your provider installer should do the following:</span></span>
  
- <span data-ttu-id="0cb67-109">验证是否提供受支持的Outlook版本。</span><span class="sxs-lookup"><span data-stu-id="0cb67-109">Verify whether a supported version of Outlook is present.</span></span>
    
- <span data-ttu-id="0cb67-110">验证是否已安装 OSC。</span><span class="sxs-lookup"><span data-stu-id="0cb67-110">Verify whether the OSC is installed.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0cb67-111">即点即用是一个虚拟环境，32 Outlook 32 (32 位) 或 Outlook 2013 (32 位) 可以运行。</span><span class="sxs-lookup"><span data-stu-id="0cb67-111">Click-to-Run is a virtual environment in which Outlook 2010 (32-bit) or Outlook 2013 (32-bit) can run.</span></span> <span data-ttu-id="0cb67-112">对于 Outlook 2013，请验证 VirtualOutlook 项是否存在于HKEY_LOCAL_MACHINE\Software\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook注册表Windows中。</span><span class="sxs-lookup"><span data-stu-id="0cb67-112">For Outlook 2013, verify if the VirtualOutlook key exists in HKEY_LOCAL_MACHINE\Software\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook of the Windows registry.</span></span> <span data-ttu-id="0cb67-113">有关在客户端计算机上Outlook即点即用产品的信息，请参阅如何验证 Outlook 是否作为即点即用产品在计算机上[可用](https://blogs.msdn.com/b/officedevdocs/archive/2010/03/09/how-to-verify-if-outlook-is-available-on-a-computer-as-a-click-to-run-product.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0cb67-113">For more information about delivering Outlook as a Click-to-Run product on a client computer, see [How to Verify if Outlook is Available on a Computer as a Click-to-Run Product](https://blogs.msdn.com/b/officedevdocs/archive/2010/03/09/how-to-verify-if-outlook-is-available-on-a-computer-as-a-click-to-run-product.aspx).</span></span> 
  
<span data-ttu-id="0cb67-114">但是，用户必须确保 OSC 在安装提供程序之前已启用。</span><span class="sxs-lookup"><span data-stu-id="0cb67-114">The user, however, has to ensure that the OSC is enabled before installing the provider.</span></span>
  
<span data-ttu-id="0cb67-115">第三方（包括 OSC 提供程序）无法重新分发 OSC。</span><span class="sxs-lookup"><span data-stu-id="0cb67-115">Third parties, including OSC providers, cannot redistribute the OSC.</span></span> <span data-ttu-id="0cb67-116">但是，如果未安装 OSC，提供程序安装程序可以使用相应的 g 链接在客户端计算机上安装 OSC。</span><span class="sxs-lookup"><span data-stu-id="0cb67-116">However, if the OSC is not installed, the provider installer can use appropriate g-links to install the OSC on the client computer.</span></span> <span data-ttu-id="0cb67-117">g-link 是专门构建的 URL，用于将用户转发 https://g.live.com 到相应的网页以下载 OSC。</span><span class="sxs-lookup"><span data-stu-id="0cb67-117">A g-link is a specially constructed URL on https://g.live.com that forwards a user to a corresponding webpage to download the OSC.</span></span> <span data-ttu-id="0cb67-118">OSC g-link 的格式设置为 https://g.live.com/0CR _LCID_ /  _Glink，_ 其中 _LCID_ 和 _Glink_ 指定客户端Outlook区域设置、版本和位。</span><span class="sxs-lookup"><span data-stu-id="0cb67-118">An OSC g-link is formatted as https://g.live.com/0CR _LCID_/ _Glink_, where  _LCID_ and  _Glink_ specify the locale, version, and bitness of Outlook on the client computer.</span></span> <span data-ttu-id="0cb67-119">每个 g 链接指向一个可执行文件，并且特定于指定的  _LCID_ 和  _Glink_ 值。</span><span class="sxs-lookup"><span data-stu-id="0cb67-119">Each g-link points to an executable and is specific to the specified  _LCID_ and  _Glink_ values.</span></span> 
  
<span data-ttu-id="0cb67-120">例如，为 LCID 1033 (美国英语) 安装 Outlook 2003 或 Outlook 2007 的 OSC 最新版本的 g 链接如下所示：</span><span class="sxs-lookup"><span data-stu-id="0cb67-120">For example, the g-link to install the latest version of the OSC for Outlook 2003 or Outlook 2007 for the LCID 1033 (US English) is as follows:</span></span>
  
https://g.live.com/0CR1033/80
  
<span data-ttu-id="0cb67-121">有关不同版本的 _Glink_ 值和 Outlook 的位值以及受支持的区域设置中的 _LCID_ 值的详细信息，请参阅下面的安装清单#7中的 [](#olosc_InstallationOverview_InstallationChecklist)#7。</span><span class="sxs-lookup"><span data-stu-id="0cb67-121">For details about  _Glink_ values for different versions and bitness of Outlook, and  _LCID_ values for supported locales, see #7 in the section [Installation Checklist](#olosc_InstallationOverview_InstallationChecklist) below.</span></span> 

<span data-ttu-id="0cb67-122"><a name="olosc_InstallationOverview_InstallationChecklist"> </a></span><span class="sxs-lookup"><span data-stu-id="0cb67-122"><a name="olosc_InstallationOverview_InstallationChecklist"> </a></span></span>

## <a name="installation-checklist"></a><span data-ttu-id="0cb67-123">安装清单</span><span class="sxs-lookup"><span data-stu-id="0cb67-123">Installation checklist</span></span>

<span data-ttu-id="0cb67-124">提供程序安装包应执行一系列安装检查，如图 1 所示，以确保提供程序安装成功。</span><span class="sxs-lookup"><span data-stu-id="0cb67-124">The provider setup package should perform a series of installation checks, as shown in Figure 1, to ensure that the provider installs successfully.</span></span>
  
<span data-ttu-id="0cb67-125">**图 1.提供程序安装逻辑**</span><span class="sxs-lookup"><span data-stu-id="0cb67-125">**Figure 1. Provider installation logic**</span></span>

![安装清单](media/odc_ol14_ta_OSC_Fig07.gif)
  
<span data-ttu-id="0cb67-127">以下过程介绍图 1 中概述的安装检查。</span><span class="sxs-lookup"><span data-stu-id="0cb67-127">The following procedure describes the installation checks outlined in Figure 1.</span></span>
  
1. <span data-ttu-id="0cb67-128">作为先决条件，检测 Outlook是已安装还是存在，如果已安装或存在，请确定 Outlook版本是否支持 OSC。</span><span class="sxs-lookup"><span data-stu-id="0cb67-128">As a prerequisite, detect whether Outlook is installed or present, and if installed or present, determine whether the version of Outlook supports the OSC.</span></span> <span data-ttu-id="0cb67-129">有关检测已安装版本的Outlook，请参阅检查安装的版本[Outlook。](https://msdn.microsoft.com/library/672fc380-a29b-4e99-9211-949fd5065723%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0cb67-129">For more information about detecting the installed version of Outlook, see [Check the Version of Outlook](https://msdn.microsoft.com/library/672fc380-a29b-4e99-9211-949fd5065723%28Office.15%29.aspx).</span></span>
    
   - <span data-ttu-id="0cb67-130">如果安装的版本的 Outlook早于 Outlook 2003，则提供程序安装过程无法完成。</span><span class="sxs-lookup"><span data-stu-id="0cb67-130">If the installed version of Outlook is earlier than Outlook 2003, the provider installation procedure cannot complete.</span></span> <span data-ttu-id="0cb67-131">在继续安装 OSC 提供程序之前Outlook用户获取受支持的版本和 OSC。</span><span class="sxs-lookup"><span data-stu-id="0cb67-131">Inform the user to obtain a supported version of Outlook and the OSC before proceeding to install the OSC provider.</span></span>
    
   - <span data-ttu-id="0cb67-132">如果未Outlook，请继续执行步骤 2。</span><span class="sxs-lookup"><span data-stu-id="0cb67-132">If Outlook is not installed, proceed to step 2.</span></span>
    
   - <span data-ttu-id="0cb67-133">如果Outlook 2003 或 Outlook 2007，请继续执行步骤 3。</span><span class="sxs-lookup"><span data-stu-id="0cb67-133">If Outlook 2003 or Outlook 2007 is installed, proceed to step 3.</span></span> 
    
   - <span data-ttu-id="0cb67-134">如果Outlook 2010 或 Outlook 2013，请继续执行步骤 4。</span><span class="sxs-lookup"><span data-stu-id="0cb67-134">If Outlook 2010 or Outlook 2013 is installed, proceed to step 4.</span></span>
    
2. <span data-ttu-id="0cb67-135">**如果未在客户端计算机Outlook，请继续执行此步骤：**</span><span class="sxs-lookup"><span data-stu-id="0cb67-135">**Proceed with this step if Outlook is not installed on the client computer:**</span></span>
    
   1. <span data-ttu-id="0cb67-136">检查 OSC 是作为 Outlook 2010 或 Outlook 2013 即点即用安装的默认组件安装的。</span><span class="sxs-lookup"><span data-stu-id="0cb67-136">Check whether the OSC is installed as a default component of a Click-to-Run installation of Outlook 2010 or Outlook 2013.</span></span> <span data-ttu-id="0cb67-137">检查 `VirtualOutlook` 注册表中以下位置Windows项：</span><span class="sxs-lookup"><span data-stu-id="0cb67-137">Examine the  `VirtualOutlook` key in the following location in the Windows registry:</span></span> 
      
      - <span data-ttu-id="0cb67-138">对于 Outlook 2010，`HKEY_LOCAL_MACHINE\Software\Microsoft\Office\14.0\Common\InstallRoot\Virtual\VirtualOutlook`</span><span class="sxs-lookup"><span data-stu-id="0cb67-138">For Outlook 2010,  `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\14.0\Common\InstallRoot\Virtual\VirtualOutlook`</span></span>
      
      - <span data-ttu-id="0cb67-139">对于 Outlook Social Connector 2013，`HKEY_LOCAL_MACHINE\Software\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook`</span><span class="sxs-lookup"><span data-stu-id="0cb67-139">For Outlook Social Connector 2013,  `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook`</span></span>
      
      <span data-ttu-id="0cb67-140">键  `VirtualOutlook` 是包含REG_SZ产品（如"en-us"）区域设置标记的变量值。</span><span class="sxs-lookup"><span data-stu-id="0cb67-140">The  `VirtualOutlook` key is a REG_SZ value that contains the locale tag, such as "en-us", of the installed product.</span></span> 
      
   2. <span data-ttu-id="0cb67-141">如果密钥不存在，Outlook客户端计算机上不存在该密钥，并且提供程序 `VirtualOutlook` 安装过程无法完成。</span><span class="sxs-lookup"><span data-stu-id="0cb67-141">If the  `VirtualOutlook` key does not exist, Outlook is not present on the client computer, and the provider installation procedure cannot complete.</span></span> <span data-ttu-id="0cb67-142">在继续安装 OSC 提供程序之前Outlook用户获取受支持的版本和 OSC。</span><span class="sxs-lookup"><span data-stu-id="0cb67-142">Inform the user to obtain a supported version of Outlook and the OSC before proceeding to install the OSC provider.</span></span> 
      
   3. <span data-ttu-id="0cb67-143">如果 `VirtualOutlook` 密钥存在，Outlook即点即用在客户端计算机上传递。</span><span class="sxs-lookup"><span data-stu-id="0cb67-143">If the  `VirtualOutlook` key does exist, Outlook was delivered by Click-to-Run on the client computer.</span></span> <span data-ttu-id="0cb67-144">继续通过检查操作系统注册表中以下位置中的项来检查 OSC 类型库Windows `OSCVersion` 版本：</span><span class="sxs-lookup"><span data-stu-id="0cb67-144">Proceed to check the installed version of the OSC type library by examining the  `OSCVersion` key in the following location in the Windows registry:</span></span> 
      
      `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\OSCVersion`
      
      <span data-ttu-id="0cb67-145">的值是一个字符串，指定 Socialprovider.dll (例如  `OSCVersion` ，"1.0"、"1.1"或"15") 。</span><span class="sxs-lookup"><span data-stu-id="0cb67-145">The value of  `OSCVersion` is a string that specifies the type library version number of Socialprovider.dll (for example, "1.0", "1.1", or "15").</span></span> 
      
   4. <span data-ttu-id="0cb67-146">如果  `OSCVersion` 为"1.0"、"1.1"或"15"，则安装 OSC 的适当版本。</span><span class="sxs-lookup"><span data-stu-id="0cb67-146">If  `OSCVersion` is "1.0", "1.1" or "15", an appropriate version of OSC is installed.</span></span> <span data-ttu-id="0cb67-147">继续执行步骤 6 以查找Outlook用户界面区域设置，以准备安装 OSC 的最新版本。</span><span class="sxs-lookup"><span data-stu-id="0cb67-147">Proceed to step 6 to find the current Outlook user interface locale to prepare for installing the latest version of the OSC.</span></span> 
      
   5. <span data-ttu-id="0cb67-148">否则  `OSCVersion` ，不包含预期值。</span><span class="sxs-lookup"><span data-stu-id="0cb67-148">Otherwise,  `OSCVersion` does not contain an expected value.</span></span> <span data-ttu-id="0cb67-149">继续执行步骤 6 以查找当前 Outlook用户界面区域设置，以准备安装 OSC 的适当版本。</span><span class="sxs-lookup"><span data-stu-id="0cb67-149">Proceed to step 6 to find the current Outlook user interface locale to prepare for installing an appropriate version of the OSC.</span></span> 
    
3. <span data-ttu-id="0cb67-150">**如果在客户端计算机上安装 Outlook 2003 或 Outlook 2007，请继续执行此步骤：**</span><span class="sxs-lookup"><span data-stu-id="0cb67-150">**Proceed with this step if Outlook 2003 or Outlook 2007 is installed on the client computer:**</span></span>
    
   1. <span data-ttu-id="0cb67-151">通过编写安装程序自定义操作来测试是否存在以下限定的组件 ID，验证是否已安装 OSC：</span><span class="sxs-lookup"><span data-stu-id="0cb67-151">Verify whether the OSC is installed by writing an installer custom action to test for the existence of the following qualified component ID:</span></span>
      
      `{A3B82DA3-8AD9-4935-AEA8-54B754459483}`
      
      <span data-ttu-id="0cb67-152">限定组件 ID 是提供单级间接寻址方法的 GUID，类似于指针。</span><span class="sxs-lookup"><span data-stu-id="0cb67-152">The qualified component ID is a GUID that provides a method of single-level indirection, similar to a pointer.</span></span> <span data-ttu-id="0cb67-153">有关安装程序Windows，请参阅[路线图Windows安装程序文档](https://docs.microsoft.com/windows/desktop/msi/roadmap-to-windows-installer-documentation)。</span><span class="sxs-lookup"><span data-stu-id="0cb67-153">For more information about Windows Installer, see [Roadmap to Windows Installer Documentation](https://docs.microsoft.com/windows/desktop/msi/roadmap-to-windows-installer-documentation).</span></span>
      
   2. <span data-ttu-id="0cb67-154">如果存在指定的限定组件，则安装 OSC 的版本。</span><span class="sxs-lookup"><span data-stu-id="0cb67-154">If the specified qualified component exists, a version of the OSC is installed.</span></span> <span data-ttu-id="0cb67-155">继续执行步骤 5 以查找当前 Outlook用户界面区域设置，以准备安装 OSC 的最新版本。</span><span class="sxs-lookup"><span data-stu-id="0cb67-155">Proceed to step 5 to find the current Outlook user interface locale to prepare for installing the latest version of the OSC.</span></span>
      
   3. <span data-ttu-id="0cb67-156">否则，不会安装 OSC。</span><span class="sxs-lookup"><span data-stu-id="0cb67-156">Otherwise, the OSC is not installed.</span></span> <span data-ttu-id="0cb67-157">继续执行步骤 6 以查找当前 Outlook用户界面区域设置，以准备安装 OSC 的适当版本。</span><span class="sxs-lookup"><span data-stu-id="0cb67-157">Proceed to step 6 to find the current Outlook user interface locale to prepare for installing an appropriate version of the OSC.</span></span>
      
4. <span data-ttu-id="0cb67-158">**如果在客户端计算机上安装 Outlook 2010 或 Outlook 2013，请继续执行此步骤：**</span><span class="sxs-lookup"><span data-stu-id="0cb67-158">**Proceed with this step if Outlook 2010 or Outlook 2013 is installed on the client computer:**</span></span>
    
   1. <span data-ttu-id="0cb67-159">通过检查注册表中以下位置的项Outlook确定已安装版本的 Windows `Bitness` 的位：</span><span class="sxs-lookup"><span data-stu-id="0cb67-159">Determine the bitness of the installed version of Outlook by examining the  `Bitness` key in the following location in the Windows registry:</span></span> 
      
      - <span data-ttu-id="0cb67-160">对于 Outlook 2010，查看`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\14.0\Outlook`</span><span class="sxs-lookup"><span data-stu-id="0cb67-160">For Outlook 2010, look at  `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\14.0\Outlook`</span></span>
      
      - <span data-ttu-id="0cb67-161">有关 Outlook 2013，查看`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Outlook`</span><span class="sxs-lookup"><span data-stu-id="0cb67-161">For Outlook 2013, look at  `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Outlook`</span></span>
      
      <span data-ttu-id="0cb67-162">对于 32 位设备，密钥为 `Bitness` "x86"，Outlook"x64"表示 64 位Outlook。</span><span class="sxs-lookup"><span data-stu-id="0cb67-162">The  `Bitness` key is "x86" for 32-bit Outlook, or "x64" for 64-bit Outlook.</span></span> 
      
   2. <span data-ttu-id="0cb67-163">如果您的提供程序是托管提供程序，并且您编译了将目标平台指定为"任何 **CPU"** 的提供程序组件，请继续执行步骤 6 以查找当前的 Outlook 用户界面区域设置，以准备安装 OSC 的最新版本。</span><span class="sxs-lookup"><span data-stu-id="0cb67-163">If your provider is a managed provider, and you compiled the provider component specifying the target platform as **Any CPU**, proceed with step 6 to find the current Outlook user interface locale to prepare for installing the latest version of the OSC.</span></span> <span data-ttu-id="0cb67-164">您的提供程序将在 32 位和 64 位版本的 OSC 上工作。</span><span class="sxs-lookup"><span data-stu-id="0cb67-164">Your provider will work on both 32-bit and 64-bit versions of the OSC.</span></span>
      
   3. <span data-ttu-id="0cb67-165">如果您的提供程序是本机 COM 组件，请检查已安装版本的 Outlook：</span><span class="sxs-lookup"><span data-stu-id="0cb67-165">If your provider is a native COM component, examine the bitness of the installed version of Outlook:</span></span>
      
      - <span data-ttu-id="0cb67-166">如果安装的 Outlook 版本为 32 位，则安装过程在确保安装了适当的 OSC 后，必须安装步骤 8) 中的 32 位提供程序 (。</span><span class="sxs-lookup"><span data-stu-id="0cb67-166">If the installed version of Outlook is 32-bit, your installation procedure will have to install a 32-bit provider (in step 8), after ensuring that an appropriate OSC is installed.</span></span>
      
      - <span data-ttu-id="0cb67-167">否则，安装的 Outlook 版本为 64 位，并且您的安装过程在确保安装了适当的 OSC 后，必须安装步骤 8) 中的 64 位提供程序 (。</span><span class="sxs-lookup"><span data-stu-id="0cb67-167">Otherwise, the installed version of Outlook is 64-bit, and your installation procedure will have to install a 64-bit provider (in step 8), after ensuring that an appropriate OSC is installed.</span></span> 
      
   4. <span data-ttu-id="0cb67-168">继续执行步骤 6 以查找当前 Outlook用户界面区域设置，以准备安装 OSC 的适当版本。</span><span class="sxs-lookup"><span data-stu-id="0cb67-168">Proceed with step 6 to find the current Outlook user interface locale to prepare for installing an appropriate version of the OSC.</span></span>
    
5. <span data-ttu-id="0cb67-169">**如果安装了 Outlook 2003 或 Outlook 2007，并且 OSC** 已安装在客户端计算机上，请继续执行此步骤：通过检查Outlook注册表中以下位置中的项，检查当前Windows `OSCLcid` 区域设置：</span><span class="sxs-lookup"><span data-stu-id="0cb67-169">**Proceed with this step if Outlook 2003 or Outlook 2007 is installed, and the OSC is installed on the client computer:** Check the current Outlook user interface locale by examining the  `OSCLcid` key in the following location in the Windows registry:</span></span> 
    
   `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\OSCLcid`
    
   <span data-ttu-id="0cb67-170">该键是一个 DWORD 值，它指定 Internet 工程任务组 (IETF) 区域设置标记 (由 `OSCLcid` [[RFC4646]](https://www.ietf.org/rfc/rfc4646.txt)和[[RFC4647]](https://www.ietf.org/rfc/rfc4647.txt)) 定义，代表当前的 Outlook 用户界面区域设置。</span><span class="sxs-lookup"><span data-stu-id="0cb67-170">The  `OSCLcid` key is a DWORD value that specifies the Internet Engineering Task Force (IETF) locale tag (defined by [[RFC4646]](https://www.ietf.org/rfc/rfc4646.txt) and [[RFC4647]](https://www.ietf.org/rfc/rfc4647.txt)), that represents the current Outlook user interface locale.</span></span> <span data-ttu-id="0cb67-171">继续执行步骤 7 以在客户端计算机上安装最新的 OSC。</span><span class="sxs-lookup"><span data-stu-id="0cb67-171">Proceed with step 7 to install the latest OSC on the client computer.</span></span>
    
6. <span data-ttu-id="0cb67-172">**如果安装了 Outlook 2003 或 Outlook 2007，或者存在 Outlook 2010 或 Outlook 2013，但不一定在客户端计算机上安装最新的 OSC，请继续执行此步骤：**</span><span class="sxs-lookup"><span data-stu-id="0cb67-172">**Proceed with this step if Outlook 2003 or Outlook 2007 is installed, or Outlook 2010 or Outlook 2013 is present, but the latest OSC is not necessarily installed on the client computer:**</span></span>
    
   <span data-ttu-id="0cb67-173">使用 **LanguageSettings** 对象可确定用户界面区域Outlook的 LCID。</span><span class="sxs-lookup"><span data-stu-id="0cb67-173">Use the **LanguageSettings** object to determine the LCID of the Outlook user interface locale.</span></span> <span data-ttu-id="0cb67-174">下面的 Visual Basic Scripting Edition (VBScript) 代码段演示如何获取 Outlook 用户界面区域设置中的 LCID。</span><span class="sxs-lookup"><span data-stu-id="0cb67-174">The following Visual Basic Scripting Edition (VBScript) code snippet demonstrates how to obtain the LCID of the Outlook user interface locale.</span></span> 
    
   ```vb
    Function GetOutlookUI_LCID()
        ' Declare variables.
        Dim msoLanguageIDUI, olApp
        msoLanguageIDUI = 2
        Set olApp = CreateObject("Outlook.Application")
        ' Return Outlook UI LCID.
        GetOutlookUI_LCID = olApp.LanguageSettings.LanguageID(msoLanguageIDUI)
    End Function
   ```

7. <span data-ttu-id="0cb67-175">**如果安装程序具有已安装版本的 OUTLOOK 的 LCID，但不一定在客户端计算机上安装最新的 OSC，请继续执行此步骤：**</span><span class="sxs-lookup"><span data-stu-id="0cb67-175">**Proceed with this step if the installer has the LCID of the installed version of Outlook, but the latest OSC is not necessarily installed on the client computer:**</span></span>
    
   <span data-ttu-id="0cb67-176">将 g-link 链接到安装程序包，以确保在客户端计算机上安装最新版本的 OSC。</span><span class="sxs-lookup"><span data-stu-id="0cb67-176">Chain a g-link into your installation package to ensure that the latest version of the OSC is installed on the client computer.</span></span> <span data-ttu-id="0cb67-177">g-link 格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="0cb67-177">The g-link format is as follows:</span></span>
    
   <span data-ttu-id="0cb67-178"> https://g.live.com/0CR_LCID_ / _Glink_</span><span class="sxs-lookup"><span data-stu-id="0cb67-178">https://g.live.com/0CR _LCID_/ _Glink_</span></span>
    
   <span data-ttu-id="0cb67-179">有关支持的  _LCID_ 值，请参阅下面的表 1，有关支持的  _Glink_ 值，请参阅表 2。</span><span class="sxs-lookup"><span data-stu-id="0cb67-179">Refer to Table 1 below for the supported  _LCID_ values, and Table 2 for the supported  _Glink_ values.</span></span> <span data-ttu-id="0cb67-180">例如，用于安装 32 位 Outlook Social Connector 2013 (美国英语) 的最新版本的 32 位 OSC 的 g 链接如下所示：</span><span class="sxs-lookup"><span data-stu-id="0cb67-180">For example, the g-link to install the latest version of the 32-bit OSC for 32-bit Outlook Social Connector 2013 (US English) is as follows:</span></span> 
    
   https://g.live.com/0CR1033/82
    
8. <span data-ttu-id="0cb67-181">安装提供程序。</span><span class="sxs-lookup"><span data-stu-id="0cb67-181">Install the provider.</span></span> <span data-ttu-id="0cb67-182">提供程序安装过程必须在适当的注册表位置 (ProgID) 编程Windows标识符。</span><span class="sxs-lookup"><span data-stu-id="0cb67-182">The provider installation procedure must register the programmatic identifier (ProgID) in the appropriate Windows registry location.</span></span> <span data-ttu-id="0cb67-183">有关详细信息，请参阅 [注册提供程序](registering-a-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="0cb67-183">For more information, see [Registering a Provider](registering-a-provider.md).</span></span> <span data-ttu-id="0cb67-184">此外，请确保要安装的提供程序的位与客户端计算机上当前Outlook版本的位相同。</span><span class="sxs-lookup"><span data-stu-id="0cb67-184">Also, be sure that the bitness of the provider to be installed is the same as the bitness of the version of Outlook present on the client computer.</span></span> <span data-ttu-id="0cb67-185">例如，如果存在 32 位 Outlook 2013，则安装 32 位提供程序;如果安装了 64 位 Outlook 2013，则安装 64 位提供程序。</span><span class="sxs-lookup"><span data-stu-id="0cb67-185">For example, install a 32-bit provider if 32-bit Outlook 2013 is present, and a 64-bit provider if 64-bit Outlook 2013 is installed.</span></span> <span data-ttu-id="0cb67-186">对于 Outlook 2003 或 2007，仅应用 32 位版本的提供程序。</span><span class="sxs-lookup"><span data-stu-id="0cb67-186">For Outlook 2003 or 2007, only the 32-bit version of your provider applies.</span></span> 
    
<span data-ttu-id="0cb67-187">**表 1：OSC 支持的十六进制区域设置和相应的 LCID 值**</span><span class="sxs-lookup"><span data-stu-id="0cb67-187">**Table 1: Supported locale and corresponding LCID values in hexadecimal for the OSC**</span></span>
  
|<span data-ttu-id="0cb67-188">**Locale**</span><span class="sxs-lookup"><span data-stu-id="0cb67-188">**Locale**</span></span>|<span data-ttu-id="0cb67-189">**LCID**</span><span class="sxs-lookup"><span data-stu-id="0cb67-189">**LCID**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0cb67-190">ar-sa</span><span class="sxs-lookup"><span data-stu-id="0cb67-190">ar-sa</span></span>  <br/> |<span data-ttu-id="0cb67-191">1025</span><span class="sxs-lookup"><span data-stu-id="0cb67-191">1025</span></span>  <br/> |
|<span data-ttu-id="0cb67-192">bg-bg</span><span class="sxs-lookup"><span data-stu-id="0cb67-192">bg-bg</span></span>  <br/> |<span data-ttu-id="0cb67-193">1026</span><span class="sxs-lookup"><span data-stu-id="0cb67-193">1026</span></span>  <br/> |
|<span data-ttu-id="0cb67-194">ca-es</span><span class="sxs-lookup"><span data-stu-id="0cb67-194">ca-es</span></span>  <br/> |<span data-ttu-id="0cb67-195">1027</span><span class="sxs-lookup"><span data-stu-id="0cb67-195">1027</span></span>  <br/> |
|<span data-ttu-id="0cb67-196">cs-cz</span><span class="sxs-lookup"><span data-stu-id="0cb67-196">cs-cz</span></span>  <br/> |<span data-ttu-id="0cb67-197">1029</span><span class="sxs-lookup"><span data-stu-id="0cb67-197">1029</span></span>  <br/> |
|<span data-ttu-id="0cb67-198">da-dk</span><span class="sxs-lookup"><span data-stu-id="0cb67-198">da-dk</span></span>  <br/> |<span data-ttu-id="0cb67-199">1030</span><span class="sxs-lookup"><span data-stu-id="0cb67-199">1030</span></span>  <br/> |
|<span data-ttu-id="0cb67-200">de-de</span><span class="sxs-lookup"><span data-stu-id="0cb67-200">de-de</span></span>  <br/> |<span data-ttu-id="0cb67-201">1031</span><span class="sxs-lookup"><span data-stu-id="0cb67-201">1031</span></span>  <br/> |
|<span data-ttu-id="0cb67-202">el-gr</span><span class="sxs-lookup"><span data-stu-id="0cb67-202">el-gr</span></span>  <br/> |<span data-ttu-id="0cb67-203">1032</span><span class="sxs-lookup"><span data-stu-id="0cb67-203">1032</span></span>  <br/> |
|<span data-ttu-id="0cb67-204">en-us</span><span class="sxs-lookup"><span data-stu-id="0cb67-204">en-us</span></span>  <br/> |<span data-ttu-id="0cb67-205">1033</span><span class="sxs-lookup"><span data-stu-id="0cb67-205">1033</span></span>  <br/> |
|<span data-ttu-id="0cb67-206">es-es</span><span class="sxs-lookup"><span data-stu-id="0cb67-206">es-es</span></span>  <br/> |<span data-ttu-id="0cb67-207">3082</span><span class="sxs-lookup"><span data-stu-id="0cb67-207">3082</span></span>  <br/> |
|<span data-ttu-id="0cb67-208">et-ee</span><span class="sxs-lookup"><span data-stu-id="0cb67-208">et-ee</span></span>  <br/> |<span data-ttu-id="0cb67-209">1061</span><span class="sxs-lookup"><span data-stu-id="0cb67-209">1061</span></span>  <br/> |
|<span data-ttu-id="0cb67-210">eu-es</span><span class="sxs-lookup"><span data-stu-id="0cb67-210">eu-es</span></span>  <br/> |<span data-ttu-id="0cb67-211">1069</span><span class="sxs-lookup"><span data-stu-id="0cb67-211">1069</span></span>  <br/> |
|<span data-ttu-id="0cb67-212">fi-fi</span><span class="sxs-lookup"><span data-stu-id="0cb67-212">fi-fi</span></span>  <br/> |<span data-ttu-id="0cb67-213">1035</span><span class="sxs-lookup"><span data-stu-id="0cb67-213">1035</span></span>  <br/> |
|<span data-ttu-id="0cb67-214">fr-fr</span><span class="sxs-lookup"><span data-stu-id="0cb67-214">fr-fr</span></span>  <br/> |<span data-ttu-id="0cb67-215">1036</span><span class="sxs-lookup"><span data-stu-id="0cb67-215">1036</span></span>  <br/> |
|<span data-ttu-id="0cb67-216">gl-es</span><span class="sxs-lookup"><span data-stu-id="0cb67-216">gl-es</span></span>  <br/> |<span data-ttu-id="0cb67-217">1110</span><span class="sxs-lookup"><span data-stu-id="0cb67-217">1110</span></span>  <br/> |
|<span data-ttu-id="0cb67-218">he-il</span><span class="sxs-lookup"><span data-stu-id="0cb67-218">he-il</span></span>  <br/> |<span data-ttu-id="0cb67-219">1037</span><span class="sxs-lookup"><span data-stu-id="0cb67-219">1037</span></span>  <br/> |
|<span data-ttu-id="0cb67-220">hi-in</span><span class="sxs-lookup"><span data-stu-id="0cb67-220">hi-in</span></span>  <br/> |<span data-ttu-id="0cb67-221">1081</span><span class="sxs-lookup"><span data-stu-id="0cb67-221">1081</span></span>  <br/> |
|<span data-ttu-id="0cb67-222">hr-hr</span><span class="sxs-lookup"><span data-stu-id="0cb67-222">hr-hr</span></span>  <br/> |<span data-ttu-id="0cb67-223">1050</span><span class="sxs-lookup"><span data-stu-id="0cb67-223">1050</span></span>  <br/> |
|<span data-ttu-id="0cb67-224">hu-hu</span><span class="sxs-lookup"><span data-stu-id="0cb67-224">hu-hu</span></span>  <br/> |<span data-ttu-id="0cb67-225">1038</span><span class="sxs-lookup"><span data-stu-id="0cb67-225">1038</span></span>  <br/> |
|<span data-ttu-id="0cb67-226">it-it</span><span class="sxs-lookup"><span data-stu-id="0cb67-226">it-it</span></span>  <br/> |<span data-ttu-id="0cb67-227">1040</span><span class="sxs-lookup"><span data-stu-id="0cb67-227">1040</span></span>  <br/> |
|<span data-ttu-id="0cb67-228">ja-jp</span><span class="sxs-lookup"><span data-stu-id="0cb67-228">ja-jp</span></span>  <br/> |<span data-ttu-id="0cb67-229">1041</span><span class="sxs-lookup"><span data-stu-id="0cb67-229">1041</span></span>  <br/> |
|<span data-ttu-id="0cb67-230">kk-kz</span><span class="sxs-lookup"><span data-stu-id="0cb67-230">kk-kz</span></span>  <br/> |<span data-ttu-id="0cb67-231">1087</span><span class="sxs-lookup"><span data-stu-id="0cb67-231">1087</span></span>  <br/> |
|<span data-ttu-id="0cb67-232">ko-kr</span><span class="sxs-lookup"><span data-stu-id="0cb67-232">ko-kr</span></span>  <br/> |<span data-ttu-id="0cb67-233">1042</span><span class="sxs-lookup"><span data-stu-id="0cb67-233">1042</span></span>  <br/> |
|<span data-ttu-id="0cb67-234">lt-lt</span><span class="sxs-lookup"><span data-stu-id="0cb67-234">lt-lt</span></span>  <br/> |<span data-ttu-id="0cb67-235">1063</span><span class="sxs-lookup"><span data-stu-id="0cb67-235">1063</span></span>  <br/> |
|<span data-ttu-id="0cb67-236">lv-lv</span><span class="sxs-lookup"><span data-stu-id="0cb67-236">lv-lv</span></span>  <br/> |<span data-ttu-id="0cb67-237">1062</span><span class="sxs-lookup"><span data-stu-id="0cb67-237">1062</span></span>  <br/> |
|<span data-ttu-id="0cb67-238">nb-no</span><span class="sxs-lookup"><span data-stu-id="0cb67-238">nb-no</span></span>  <br/> |<span data-ttu-id="0cb67-239">1044</span><span class="sxs-lookup"><span data-stu-id="0cb67-239">1044</span></span>  <br/> |
|<span data-ttu-id="0cb67-240">nl-nl</span><span class="sxs-lookup"><span data-stu-id="0cb67-240">nl-nl</span></span>  <br/> |<span data-ttu-id="0cb67-241">1043</span><span class="sxs-lookup"><span data-stu-id="0cb67-241">1043</span></span>  <br/> |
|<span data-ttu-id="0cb67-242">pl-pl</span><span class="sxs-lookup"><span data-stu-id="0cb67-242">pl-pl</span></span>  <br/> |<span data-ttu-id="0cb67-243">1045</span><span class="sxs-lookup"><span data-stu-id="0cb67-243">1045</span></span>  <br/> |
|<span data-ttu-id="0cb67-244">pt-br</span><span class="sxs-lookup"><span data-stu-id="0cb67-244">pt-br</span></span>  <br/> |<span data-ttu-id="0cb67-245">1046</span><span class="sxs-lookup"><span data-stu-id="0cb67-245">1046</span></span>  <br/> |
|<span data-ttu-id="0cb67-246">pt-pt</span><span class="sxs-lookup"><span data-stu-id="0cb67-246">pt-pt</span></span>  <br/> |<span data-ttu-id="0cb67-247">2070</span><span class="sxs-lookup"><span data-stu-id="0cb67-247">2070</span></span>  <br/> |
|<span data-ttu-id="0cb67-248">ro-ro</span><span class="sxs-lookup"><span data-stu-id="0cb67-248">ro-ro</span></span>  <br/> |<span data-ttu-id="0cb67-249">1048</span><span class="sxs-lookup"><span data-stu-id="0cb67-249">1048</span></span>  <br/> |
|<span data-ttu-id="0cb67-250">ru-ru</span><span class="sxs-lookup"><span data-stu-id="0cb67-250">ru-ru</span></span>  <br/> |<span data-ttu-id="0cb67-251">1049</span><span class="sxs-lookup"><span data-stu-id="0cb67-251">1049</span></span>  <br/> |
|<span data-ttu-id="0cb67-252">sk-sk</span><span class="sxs-lookup"><span data-stu-id="0cb67-252">sk-sk</span></span>  <br/> |<span data-ttu-id="0cb67-253">1051</span><span class="sxs-lookup"><span data-stu-id="0cb67-253">1051</span></span>  <br/> |
|<span data-ttu-id="0cb67-254">sl-si</span><span class="sxs-lookup"><span data-stu-id="0cb67-254">sl-si</span></span>  <br/> |<span data-ttu-id="0cb67-255">1060</span><span class="sxs-lookup"><span data-stu-id="0cb67-255">1060</span></span>  <br/> |
|<span data-ttu-id="0cb67-256">sr-cyrl-cs</span><span class="sxs-lookup"><span data-stu-id="0cb67-256">sr-cyrl-cs</span></span>  <br/> |<span data-ttu-id="0cb67-257">3098</span><span class="sxs-lookup"><span data-stu-id="0cb67-257">3098</span></span>  <br/> |
|<span data-ttu-id="0cb67-258">sr-latn-cs</span><span class="sxs-lookup"><span data-stu-id="0cb67-258">sr-latn-cs</span></span>  <br/> |<span data-ttu-id="0cb67-259">2074</span><span class="sxs-lookup"><span data-stu-id="0cb67-259">2074</span></span>  <br/> |
|<span data-ttu-id="0cb67-260">sv-se</span><span class="sxs-lookup"><span data-stu-id="0cb67-260">sv-se</span></span>  <br/> |<span data-ttu-id="0cb67-261">1053</span><span class="sxs-lookup"><span data-stu-id="0cb67-261">1053</span></span>  <br/> |
|<span data-ttu-id="0cb67-262">th-th</span><span class="sxs-lookup"><span data-stu-id="0cb67-262">th-th</span></span>  <br/> |<span data-ttu-id="0cb67-263">1054</span><span class="sxs-lookup"><span data-stu-id="0cb67-263">1054</span></span>  <br/> |
|<span data-ttu-id="0cb67-264">tr-tr</span><span class="sxs-lookup"><span data-stu-id="0cb67-264">tr-tr</span></span>  <br/> |<span data-ttu-id="0cb67-265">1055</span><span class="sxs-lookup"><span data-stu-id="0cb67-265">1055</span></span>  <br/> |
|<span data-ttu-id="0cb67-266">uk-ua</span><span class="sxs-lookup"><span data-stu-id="0cb67-266">uk-ua</span></span>  <br/> |<span data-ttu-id="0cb67-267">1058</span><span class="sxs-lookup"><span data-stu-id="0cb67-267">1058</span></span>  <br/> |
|<span data-ttu-id="0cb67-268">zh-cn</span><span class="sxs-lookup"><span data-stu-id="0cb67-268">zh-cn</span></span>  <br/> |<span data-ttu-id="0cb67-269">2052</span><span class="sxs-lookup"><span data-stu-id="0cb67-269">2052</span></span>  <br/> |
|<span data-ttu-id="0cb67-270">zh-tw</span><span class="sxs-lookup"><span data-stu-id="0cb67-270">zh-tw</span></span>  <br/> |<span data-ttu-id="0cb67-271">1028</span><span class="sxs-lookup"><span data-stu-id="0cb67-271">1028</span></span>  <br/> |
   
<span data-ttu-id="0cb67-272">**表 2：OSC 支持的 Glink 值**</span><span class="sxs-lookup"><span data-stu-id="0cb67-272">**Table 2: Supported Glink values for the OSC**</span></span>
  
|<span data-ttu-id="0cb67-273">**Glink 值**</span><span class="sxs-lookup"><span data-stu-id="0cb67-273">**Glink value**</span></span>|<span data-ttu-id="0cb67-274">**Function**</span><span class="sxs-lookup"><span data-stu-id="0cb67-274">**Function**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0cb67-275">80</span><span class="sxs-lookup"><span data-stu-id="0cb67-275">80</span></span>  <br/> |<span data-ttu-id="0cb67-276">安装 2003 或 Outlook 2007 Outlook OSC 的最新版本。</span><span class="sxs-lookup"><span data-stu-id="0cb67-276">Installs the latest version of OSC for Outlook 2003 or Outlook 2007.</span></span>  <br/> |
|<span data-ttu-id="0cb67-277">82</span><span class="sxs-lookup"><span data-stu-id="0cb67-277">82</span></span>  <br/> |<span data-ttu-id="0cb67-278">为 Outlook 2007、Outlook 2010 或 Outlook Social Connector 2013 安装最新的 32 位 OSC 修补程序。</span><span class="sxs-lookup"><span data-stu-id="0cb67-278">Installs the latest patch of 32-bit OSC for Outlook 2007, Outlook 2010, or Outlook Social Connector 2013.</span></span>  <br/> |
|<span data-ttu-id="0cb67-279">83</span><span class="sxs-lookup"><span data-stu-id="0cb67-279">83</span></span>  <br/> |<span data-ttu-id="0cb67-280">安装适用于 2010 或 Outlook Social Connector 2013 Outlook 64 位 OSC 的最新修补程序。</span><span class="sxs-lookup"><span data-stu-id="0cb67-280">Installs the latest patch of 64-bit OSC for Outlook 2010 or Outlook Social Connector 2013.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0cb67-281">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0cb67-281">See also</span></span>

- [<span data-ttu-id="0cb67-282">注册提供程序</span><span class="sxs-lookup"><span data-stu-id="0cb67-282">Registering a Provider</span></span>](registering-a-provider.md) 
- [<span data-ttu-id="0cb67-283">学习开发提供程序的快速步骤</span><span class="sxs-lookup"><span data-stu-id="0cb67-283">Quick Steps for Learning to Develop a Provider</span></span>](quick-steps-for-learning-to-develop-a-provider.md)
- [<span data-ttu-id="0cb67-284">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="0cb67-284">Deploying a Provider</span></span>](deploying-a-provider.md)

