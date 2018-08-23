---
title: 安装清单
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9dfb9b6d-2fb4-45bf-a12f-bd10a799ce29
description: 本主题介绍成功安装 Outlook Social Connector (OSC) 提供程序的先决条件和安装检查提供程序安装程序应完成正常工作。
ms.openlocfilehash: d9854bf5c2b524c6d735fe974046583dab990012
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593996"
---
# <a name="installation-checklist"></a>安装清单

本主题介绍成功安装 Outlook Social Connector (OSC) 提供程序的先决条件和安装检查提供程序安装程序应完成正常工作。
  
## <a name="installation-overview"></a>安装概述

用户应安装 OSC 提供程序，才支持版本的 Outlook 存在和 OSC 已安装并启用客户端计算机上。 支持版本的 Outlook 的 Office Outlook 2003、 Office Outlook 2007、 Outlook 2010 和 Outlook 2013 （安装在客户端计算机，或者，对于 Outlook 2010 和 Outlook 2013，由单击即点即用分发客户端计算机上）。 若要确保成功安装，提供程序安装程序应执行以下操作：
  
- 验证受支持的版本的 Outlook 是否存在。
    
- 验证是否已安装 OSC。
    
> [!NOTE]
> 单击即点即用是 Outlook 2010 （32 位） 或 Outlook 2013 (32-bit) 可以运行的虚拟环境。 Outlook 2013 的验证 HKEY_LOCAL_MACHINE\Software\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook Windows 注册表中是否存在 VirtualOutlook 项。 有关以客户端计算机上单击即点即用产品形式提供 Outlook 的详细信息，请参阅[如何验证 Outlook 是否以即点即用产品形式的计算机上提供](http://blogs.msdn.com/b/officedevdocs/archive/2010/03/09/how-to-verify-if-outlook-is-available-on-a-computer-as-a-click-to-run-product.aspx)。 
  
但是，用户必须确保 OSC 提供程序在安装之前已启用。
  
第三方，包括 OSC 提供程序不能重新发布 OSC。 但是，如果未安装 OSC，提供程序安装程序可以使用适当的 g 链接客户端计算机上安装 OSC。 G 链接专门构建的 URL 位于http://g.live.com的转发到相应的网页用户下载 OSC。 OSC g 链接的格式设置为http://g.live.com/0CR _LCID_/ _Glink_，其中_LCID_和_Glink_指定区域设置、 版本和 Outlook 客户端计算机上的位数。 每个 g 链接指向可执行文件和特定于指定的_LCID_和_Glink_值。 
  
例如，g 链接以安装用于 Outlook 2003 OSC 或 LCID 1033 英语 （美国） 的 Outlook 2007 的最新版本的是，如下所示：
  
http://g.live.com/0CR1033/80
  
有关不同版本和位数的 Outlook， _Glink_值和支持的区域设置的_LCID_值的详细信息，请参阅[安装清单](#olosc_InstallationOverview_InstallationChecklist)下面一节中的 #7。 

<a name="olosc_InstallationOverview_InstallationChecklist"> </a>

## <a name="installation-checklist"></a>安装清单

提供程序安装程序包应执行一系列安装检查以确保提供程序成功安装图 1 中所示。
  
**图 1。提供程序安装逻辑**

![安装清单](media/odc_ol14_ta_OSC_Fig07.gif)
  
以下过程介绍安装检查图 1 所示。
  
1. 作为先决条件，检测是否安装了 Outlook 或存在，并且如果已安装或存在此参数，确定 Outlook 版本是否支持 OSC。 检测已安装的 Outlook 版本的详细信息，请参阅[检查 Outlook 版本](http://msdn.microsoft.com/library/672fc380-a29b-4e99-9211-949fd5065723%28Office.15%29.aspx)。
    
   - 如果安装的 Outlook 版本早于 Outlook 2003，无法完成的提供程序安装过程。 通知用户获取 Outlook 和然后再继续 OSC 安装 OSC 提供程序的受支持的版本。
    
   - 如果未安装 Outlook，继续执行步骤 2。
    
   - 如果安装了 Outlook 2003 或 Outlook 2007，继续执行步骤 3。 
    
   - 如果安装了 Outlook 2010 或 Outlook 2013，请继续步骤 4。
    
2. **如果客户端计算机上未安装 Outlook，则继续此步骤：**
    
   1. 检查是否为默认组件单击即点即用安装 Outlook 2010 或 Outlook 2013 的安装 OSC。 检查`VirtualOutlook`Windows 注册表中的以下位置中的键： 
      
      - Outlook 2010`HKEY_LOCAL_MACHINE\Software\Microsoft\Office\14.0\Common\InstallRoot\Virtual\VirtualOutlook`
      
      - 为 Outlook Social Connector 2013`HKEY_LOCAL_MACHINE\Software\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook`
      
      `VirtualOutlook`项是一个 REG_SZ 值，包含区域设置标记，如"en-我们"，已安装的产品。 
      
   2. 如果`VirtualOutlook`项不存在，Outlook 不存在的客户端计算机上，并提供程序安装过程无法完成。 通知用户获取 Outlook 和然后再继续 OSC 安装 OSC 提供程序的受支持的版本。 
      
   3. 如果`VirtualOutlook`密钥是否存在、 Outlook 已由单击即点即用分发客户端计算机上。 继续通过检查检查安装的 OSC 类型库的版本`OSCVersion`Windows 注册表中的以下位置中的键： 
      
      `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\OSCVersion`
      
      值`OSCVersion`是一个字符串，指定 Socialprovider.dll （例如，"1.0"、"1.1"或"15"） 的类型库版本号。 
      
   4. 如果`OSCVersion`"1.0"、"1.1"15"，安装相应版本的 OSC。 继续执行步骤 6 以查找当前的 Outlook 用户界面区域，准备安装 OSC 的最新版本。 
      
   5. 否则为`OSCVersion`不包含预期值。 继续执行步骤 6 以查找当前的 Outlook 用户界面区域，准备安装相应版本 OSC。 
    
3. **如果客户端计算机上安装了 Outlook 2003 或 Outlook 2007，则继续此步骤：**
    
   1. 验证是否安装了 OSC 通过编写安装程序测试是否存在以下限定的组件 ID 的自定义操作：
      
      `{A3B82DA3-8AD9-4935-AEA8-54B754459483}`
      
      限定的组件 ID 是一种方法的单级间接寻址，类似于指针的 GUID。 有关 Windows Installer 的详细信息，请参阅[Windows Installer 文档路线图](https://docs.microsoft.com/en-us/windows/desktop/msi/roadmap-to-windows-installer-documentation)。
      
   2. 如果存在指定合格的组件，安装 OSC 的版本。 继续执行步骤 5 以查找当前的 Outlook 用户界面区域，准备安装 OSC 的最新版本。
      
   3. 否则，未安装 OSC。 继续执行步骤 6 以查找当前的 Outlook 用户界面区域，准备安装相应版本 OSC。
      
4. **如果客户端计算机上安装了 Outlook 2010 或 Outlook 2013，继续此步骤：**
    
   1. 通过检查确定安装的 Outlook 版本位数`Bitness`Windows 注册表中的以下位置中的键： 
      
      - 为 Outlook 2010 中，查看`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\14.0\Outlook`
      
      - 为 Outlook 2013 一下`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Outlook`
      
      `Bitness`密钥是 32 位 Outlook 或 64 位 outlook 的"x64"的"x86"。 
      
   2. 如果您的提供商托管提供程序，并且编译为**任何 CPU**指定目标平台的提供程序组件，继续执行步骤 6 以查找当前的 Outlook 用户界面区域，准备安装 OSC 的最新版本。 将用于 32 位和 64 位版本的 OSC 提供程序。
      
   3. 如果您的提供商是本机 COM 组件，检查安装的 Outlook 版本的位：
      
      - 如果安装的 Outlook 版本，32 位安装过程将需要确保安装了相应 OSC 后安装 32 位 （在步骤 8），提供程序。
      
      - 否则为安装的 Outlook 版本是 64 位，并且安装过程必须确保安装了相应 OSC 后安装 64 位 （在步骤 8），提供程序。 
      
   4. 继续执行步骤 6 以查找当前的 Outlook 用户界面区域，准备安装相应版本 OSC。
    
5. **继续此步骤，如果安装了 Outlook 2003 或 Outlook 2007，并且客户端计算机上安装 OSC:** 通过检查检查当前 Outlook 用户界面的区域设置`OSCLcid`Windows 注册表中的以下位置中的键： 
    
   `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\OSCLcid`
    
   `OSCLcid`项是一个 DWORD 值，该值指定 （由[[RFC4646]](http://www.ietf.org/rfc/rfc4646.txt)和[[RFC4647]](http://www.ietf.org/rfc/rfc4647.txt)定义） 的 Internet 工程任务组 (IETF) 区域设置标记，表示当前 Outlook 用户界面的区域设置。 继续步骤 7 客户端计算机上安装最新 OSC。
    
6. **如果安装了 Outlook 2003 或 Outlook 2007，或 Outlook 2010 或 Outlook 2013 已存在此参数，但未最新 OSC 一定客户端计算机上安装，则继续此步骤：**
    
   使用**LanguageSettings**对象确定 Outlook 用户界面区域设置的 LCID。 下面的 Visual Basic Scripting Edition (VBScript) 代码段演示如何获取 Outlook 用户界面区域设置的 LCID。 
    
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

7. **如果安装程序已安装的 Outlook 版本的 LCID 但未最新 OSC 一定客户端计算机上安装，则继续此步骤：**
    
   链接到您安装的程序包以确保客户端计算机上安装了最新版本的 OSC g 链接。 G 链接格式如下所示：
    
   http://g.live.com/0CR_LCID_/  _Glink_
    
   请参阅下面的受支持的_LCID_值的表 1 和表 2 的受支持的_Glink_值。 例如，g 链接以安装 32 位 Outlook Social Connector 2013 英语 （美国） 的最新版本的 32 位 OSC 如下所示： 
    
   http://g.live.com/0CR1033/82
    
8. 安装提供程序。 提供程序安装过程必须在相应的 Windows 注册表位置中注册的编程标识符 (ProgID)。 有关详细信息，请参阅[注册提供程序](registering-a-provider.md)。 另外，确保要安装的提供程序的位数是相同的客户端计算机上存在的 Outlook 版本的位数。 例如，如果安装 64 位 Outlook 2013 安装 32 位提供程序是否存在此参数，32 位 Outlook 2013 和 64 位提供程序。 对于 Outlook 2003 或 2007年，您的提供商的 32 位版本适用。 
    
**表 1： 支持的区域设置和 OSC 的十六进制数中相应的 LCID 值**
  
|**区域设置**|**LCID**|
|:-----|:-----|
|ar-sa  <br/> |1025  <br/> |
|bg-bg  <br/> |1026  <br/> |
|ca es  <br/> |1027  <br/> |
|cs-cz  <br/> |1029  <br/> |
|da-dk  <br/> |1030  <br/> |
|de-de  <br/> |1031  <br/> |
|el-gr  <br/> |1032  <br/> |
|en-us  <br/> |1033  <br/> |
|es-es  <br/> |3082  <br/> |
|et-ee  <br/> |1061  <br/> |
|欧盟 es  <br/> |1069  <br/> |
|fi-fi  <br/> |1035  <br/> |
|fr-fr  <br/> |1036  <br/> |
|总帐 es  <br/> |1110  <br/> |
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
|sr-符号 cs  <br/> |3098  <br/> |
|sr-latn cs  <br/> |2074  <br/> |
|sv-se  <br/> |1053  <br/> |
|th-th  <br/> |1054  <br/> |
|tr-tr  <br/> |1055  <br/> |
|uk-ua  <br/> |1058  <br/> |
|zh-cn  <br/> |2052  <br/> |
|zh-tw  <br/> |1028  <br/> |
   
**表 2： 支持 OSC Glink 值**
  
|**Glink 值**|**函数**|
|:-----|:-----|
|80  <br/> |安装最新版本的 Outlook 2003 或 Outlook 2007 的 OSC。  <br/> |
|82  <br/> |安装 Outlook 2007、 Outlook 2010 或 Outlook Social Connector 2013 32 位 OSC 最新修补程序。  <br/> |
|83  <br/> |安装最新的 Outlook 2010 或 Outlook Social Connector 2013 的 64 位 OSC 修补程序。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [注册提供程序](registering-a-provider.md) 
- [快速学习开发提供程序的步骤](quick-steps-for-learning-to-develop-a-provider.md)
- [部署提供程序](deploying-a-provider.md)

