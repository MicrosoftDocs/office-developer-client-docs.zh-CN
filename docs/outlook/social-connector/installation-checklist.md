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
# <a name="installation-checklist"></a>安装清单

本主题介绍成功安装 Outlook Social Connector (OSC) 提供程序的先决条件，以及您的提供程序安装程序应完成安装检查以正确工作的先决条件。
  
## <a name="installation-overview"></a>安装概述

只有在存在支持版本的 OSC 提供程序Outlook在客户端计算机上安装和启用 OSC 时，用户才应安装 OSC 提供程序。 支持版本的 Outlook 是安装在客户端计算机上的 Office Outlook 2003、Office Outlook 2007、Outlook 2010 和 Outlook 2013 (，对于 Outlook 2010 和 Outlook 2013，则由客户端计算机) 上的即点即用提供。 为了确保成功安装，提供程序安装程序应执行以下操作：
  
- 验证是否提供受支持的Outlook版本。
    
- 验证是否已安装 OSC。
    
> [!NOTE]
> 即点即用是一个虚拟环境，32 Outlook 32 (32 位) 或 Outlook 2013 (32 位) 可以运行。 对于 Outlook 2013，请验证 VirtualOutlook 项是否存在于HKEY_LOCAL_MACHINE\Software\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook注册表Windows中。 有关在客户端计算机上Outlook即点即用产品的信息，请参阅如何验证 Outlook 是否作为即点即用产品在计算机上[可用](https://blogs.msdn.com/b/officedevdocs/archive/2010/03/09/how-to-verify-if-outlook-is-available-on-a-computer-as-a-click-to-run-product.aspx)。 
  
但是，用户必须确保 OSC 在安装提供程序之前已启用。
  
第三方（包括 OSC 提供程序）无法重新分发 OSC。 但是，如果未安装 OSC，提供程序安装程序可以使用相应的 g 链接在客户端计算机上安装 OSC。 g-link 是专门构建的 URL，用于将用户转发 https://g.live.com 到相应的网页以下载 OSC。 OSC g-link 的格式设置为 https://g.live.com/0CR _LCID_ /  _Glink，_ 其中 _LCID_ 和 _Glink_ 指定客户端Outlook区域设置、版本和位。 每个 g 链接指向一个可执行文件，并且特定于指定的  _LCID_ 和  _Glink_ 值。 
  
例如，为 LCID 1033 (美国英语) 安装 Outlook 2003 或 Outlook 2007 的 OSC 最新版本的 g 链接如下所示：
  
https://g.live.com/0CR1033/80
  
有关不同版本的 _Glink_ 值和 Outlook 的位值以及受支持的区域设置中的 _LCID_ 值的详细信息，请参阅下面的安装清单#7中的 [](#olosc_InstallationOverview_InstallationChecklist)#7。 

<a name="olosc_InstallationOverview_InstallationChecklist"> </a>

## <a name="installation-checklist"></a>安装清单

提供程序安装包应执行一系列安装检查，如图 1 所示，以确保提供程序安装成功。
  
**图 1.提供程序安装逻辑**

![安装清单](media/odc_ol14_ta_OSC_Fig07.gif)
  
以下过程介绍图 1 中概述的安装检查。
  
1. 作为先决条件，检测 Outlook是已安装还是存在，如果已安装或存在，请确定 Outlook版本是否支持 OSC。 有关检测已安装版本的Outlook，请参阅检查安装的版本[Outlook。](https://msdn.microsoft.com/library/672fc380-a29b-4e99-9211-949fd5065723%28Office.15%29.aspx)
    
   - 如果安装的版本的 Outlook早于 Outlook 2003，则提供程序安装过程无法完成。 在继续安装 OSC 提供程序之前Outlook用户获取受支持的版本和 OSC。
    
   - 如果未Outlook，请继续执行步骤 2。
    
   - 如果Outlook 2003 或 Outlook 2007，请继续执行步骤 3。 
    
   - 如果Outlook 2010 或 Outlook 2013，请继续执行步骤 4。
    
2. **如果未在客户端计算机Outlook，请继续执行此步骤：**
    
   1. 检查 OSC 是作为 Outlook 2010 或 Outlook 2013 即点即用安装的默认组件安装的。 检查 `VirtualOutlook` 注册表中以下位置Windows项： 
      
      - 对于 Outlook 2010，`HKEY_LOCAL_MACHINE\Software\Microsoft\Office\14.0\Common\InstallRoot\Virtual\VirtualOutlook`
      
      - 对于 Outlook Social Connector 2013，`HKEY_LOCAL_MACHINE\Software\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook`
      
      键  `VirtualOutlook` 是包含REG_SZ产品（如"en-us&quot;）区域设置标记的变量值。 
      
   2. 如果密钥不存在，Outlook客户端计算机上不存在该密钥，并且提供程序 `VirtualOutlook` 安装过程无法完成。 在继续安装 OSC 提供程序之前Outlook用户获取受支持的版本和 OSC。 
      
   3. 如果 `VirtualOutlook` 密钥存在，Outlook即点即用在客户端计算机上传递。 继续通过检查操作系统注册表中以下位置中的项来检查 OSC 类型库Windows `OSCVersion` 版本： 
      
      `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\OSCVersion`
      
      的值是一个字符串，指定 Socialprovider.dll (例如  `OSCVersion` ，&quot;1.0&quot;、&quot;1.1&quot;或&quot;15") 。 
      
   4. 如果  `OSCVersion` 为"1.0"、"1.1"或"15"，则安装 OSC 的适当版本。 继续执行步骤 6 以查找Outlook用户界面区域设置，以准备安装 OSC 的最新版本。 
      
   5. 否则  `OSCVersion` ，不包含预期值。 继续执行步骤 6 以查找当前 Outlook用户界面区域设置，以准备安装 OSC 的适当版本。 
    
3. **如果在客户端计算机上安装 Outlook 2003 或 Outlook 2007，请继续执行此步骤：**
    
   1. 通过编写安装程序自定义操作来测试是否存在以下限定的组件 ID，验证是否已安装 OSC：
      
      `{A3B82DA3-8AD9-4935-AEA8-54B754459483}`
      
      限定组件 ID 是提供单级间接寻址方法的 GUID，类似于指针。 有关安装程序Windows，请参阅[路线图Windows安装程序文档](https://docs.microsoft.com/windows/desktop/msi/roadmap-to-windows-installer-documentation)。
      
   2. 如果存在指定的限定组件，则安装 OSC 的版本。 继续执行步骤 5 以查找当前 Outlook用户界面区域设置，以准备安装 OSC 的最新版本。
      
   3. 否则，不会安装 OSC。 继续执行步骤 6 以查找当前 Outlook用户界面区域设置，以准备安装 OSC 的适当版本。
      
4. **如果在客户端计算机上安装 Outlook 2010 或 Outlook 2013，请继续执行此步骤：**
    
   1. 通过检查注册表中以下位置的项Outlook确定已安装版本的 Windows `Bitness` 的位： 
      
      - 对于 Outlook 2010，查看`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\14.0\Outlook`
      
      - 有关 Outlook 2013，查看`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Outlook`
      
      对于 32 位设备，密钥为 `Bitness` "x86"，Outlook"x64"表示 64 位Outlook。 
      
   2. 如果您的提供程序是托管提供程序，并且您编译了将目标平台指定为"任何 **CPU"** 的提供程序组件，请继续执行步骤 6 以查找当前的 Outlook 用户界面区域设置，以准备安装 OSC 的最新版本。 您的提供程序将在 32 位和 64 位版本的 OSC 上工作。
      
   3. 如果您的提供程序是本机 COM 组件，请检查已安装版本的 Outlook：
      
      - 如果安装的 Outlook 版本为 32 位，则安装过程在确保安装了适当的 OSC 后，必须安装步骤 8) 中的 32 位提供程序 (。
      
      - 否则，安装的 Outlook 版本为 64 位，并且您的安装过程在确保安装了适当的 OSC 后，必须安装步骤 8) 中的 64 位提供程序 (。 
      
   4. 继续执行步骤 6 以查找当前 Outlook用户界面区域设置，以准备安装 OSC 的适当版本。
    
5. **如果安装了 Outlook 2003 或 Outlook 2007，并且 OSC** 已安装在客户端计算机上，请继续执行此步骤：通过检查Outlook注册表中以下位置中的项，检查当前Windows `OSCLcid` 区域设置： 
    
   `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\OSCLcid`
    
   该键是一个 DWORD 值，它指定 Internet 工程任务组 (IETF) 区域设置标记 (由 `OSCLcid` [[RFC4646]](https://www.ietf.org/rfc/rfc4646.txt)和[[RFC4647]](https://www.ietf.org/rfc/rfc4647.txt)) 定义，代表当前的 Outlook 用户界面区域设置。 继续执行步骤 7 以在客户端计算机上安装最新的 OSC。
    
6. **如果安装了 Outlook 2003 或 Outlook 2007，或者存在 Outlook 2010 或 Outlook 2013，但不一定在客户端计算机上安装最新的 OSC，请继续执行此步骤：**
    
   使用 **LanguageSettings** 对象可确定用户界面区域Outlook的 LCID。 下面的 Visual Basic Scripting Edition (VBScript) 代码段演示如何获取 Outlook 用户界面区域设置中的 LCID。 
    
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

7. **如果安装程序具有已安装版本的 OUTLOOK 的 LCID，但不一定在客户端计算机上安装最新的 OSC，请继续执行此步骤：**
    
   将 g-link 链接到安装程序包，以确保在客户端计算机上安装最新版本的 OSC。 g-link 格式如下所示：
    
   https://g.live.com/0CR_LCID_ / _Glink_
    
   有关支持的  _LCID_ 值，请参阅下面的表 1，有关支持的  _Glink_ 值，请参阅表 2。 例如，用于安装 32 位 Outlook Social Connector 2013 (美国英语) 的最新版本的 32 位 OSC 的 g 链接如下所示： 
    
   https://g.live.com/0CR1033/82
    
8. 安装提供程序。 提供程序安装过程必须在适当的注册表位置 (ProgID) 编程Windows标识符。 有关详细信息，请参阅 [注册提供程序](registering-a-provider.md)。 此外，请确保要安装的提供程序的位与客户端计算机上当前Outlook版本的位相同。 例如，如果存在 32 位 Outlook 2013，则安装 32 位提供程序;如果安装了 64 位 Outlook 2013，则安装 64 位提供程序。 对于 Outlook 2003 或 2007，仅应用 32 位版本的提供程序。 
    
**表 1：OSC 支持的十六进制区域设置和相应的 LCID 值**
  
|**Locale**|**LCID**|
|:-----|:-----|
|ar-sa  <br/> |1025  <br/> |
|bg-bg  <br/> |1026  <br/> |
|ca-es  <br/> |1027  <br/> |
|cs-cz  <br/> |1029  <br/> |
|da-dk  <br/> |1030  <br/> |
|de-de  <br/> |1031  <br/> |
|el-gr  <br/> |1032  <br/> |
|en-us  <br/> |1033  <br/> |
|es-es  <br/> |3082  <br/> |
|et-ee  <br/> |1061  <br/> |
|eu-es  <br/> |1069  <br/> |
|fi-fi  <br/> |1035  <br/> |
|fr-fr  <br/> |1036  <br/> |
|gl-es  <br/> |1110  <br/> |
|he-il  <br/> |1037  <br/> |
|hi-in  <br/> |1081  <br/> |
|hr-hr  <br/> |1050  <br/> |
|hu-hu  <br/> |1038  <br/> |
|it-it  <br/> |1040  <br/> |
|ja-jp  <br/> |1041  <br/> |
|kk-kz  <br/> |1087  <br/> |
|ko-kr  <br/> |1042  <br/> |
|lt-lt  <br/> |1063  <br/> |
|lv-lv  <br/> |1062  <br/> |
|nb-no  <br/> |1044  <br/> |
|nl-nl  <br/> |1043  <br/> |
|pl-pl  <br/> |1045  <br/> |
|pt-br  <br/> |1046  <br/> |
|pt-pt  <br/> |2070  <br/> |
|ro-ro  <br/> |1048  <br/> |
|ru-ru  <br/> |1049  <br/> |
|sk-sk  <br/> |1051  <br/> |
|sl-si  <br/> |1060  <br/> |
|sr-cyrl-cs  <br/> |3098  <br/> |
|sr-latn-cs  <br/> |2074  <br/> |
|sv-se  <br/> |1053  <br/> |
|th-th  <br/> |1054  <br/> |
|tr-tr  <br/> |1055  <br/> |
|uk-ua  <br/> |1058  <br/> |
|zh-cn  <br/> |2052  <br/> |
|zh-tw  <br/> |1028  <br/> |
   
**表 2：OSC 支持的 Glink 值**
  
|**Glink 值**|**Function**|
|:-----|:-----|
|80  <br/> |安装 2003 或 Outlook 2007 Outlook OSC 的最新版本。  <br/> |
|82  <br/> |为 Outlook 2007、Outlook 2010 或 Outlook Social Connector 2013 安装最新的 32 位 OSC 修补程序。  <br/> |
|83  <br/> |安装适用于 2010 或 Outlook Social Connector 2013 Outlook 64 位 OSC 的最新修补程序。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [注册提供程序](registering-a-provider.md) 
- [学习开发提供程序的快速步骤](quick-steps-for-learning-to-develop-a-provider.md)
- [部署提供程序](deploying-a-provider.md)

