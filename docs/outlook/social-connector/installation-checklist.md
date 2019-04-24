---
title: 安装清单
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9dfb9b6d-2fb4-45bf-a12f-bd10a799ce29
description: 本主题介绍成功安装 Outlook Social Connector (.osc) 提供程序的先决条件, 并且安装将检查提供程序安装程序是否应完成正常工作。
ms.openlocfilehash: 8fec8523e57ad2678d02a0c5cbc1ad57340e5267
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286336"
---
# <a name="installation-checklist"></a>安装清单

本主题介绍成功安装 Outlook Social Connector (.osc) 提供程序的先决条件, 并且安装将检查提供程序安装程序是否应完成正常工作。
  
## <a name="installation-overview"></a>安装概述

仅当存在支持的 Outlook 版本且在客户端计算机上安装并启用了 .osc 时, 用户才应安装 .osc 提供程序。 支持的 outlook 版本包括 office outlook 2003、office outlook 2007、Outlook 2010 和 outlook 2013 (安装在客户端计算机上, 或者在客户端计算机上由即点即用的 outlook 2010 提供)。 若要确保成功安装, 提供程序安装程序应执行以下操作:
  
- 验证是否存在受支持的 Outlook 版本。
    
- 验证是否已安装 .osc。
    
> [!NOTE]
> 即点即用是一种虚拟环境, 在该环境中, outlook 2010 (32 位) 或 outlook 2013 (32-bit) 可以运行。 对于 Outlook 2013, 请验证 VirtualOutlook 项是否存在于 HKEY_LOCAL_MACHINE\Software\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook 的 Windows 注册表中。 有关在客户端计算机上将 outlook 作为即点即用产品进行传递的详细信息, 请参阅[如何验证 outlook 在计算机上是否可用作即点](https://blogs.msdn.com/b/officedevdocs/archive/2010/03/09/how-to-verify-if-outlook-is-available-on-a-computer-as-a-click-to-run-product.aspx)即用产品。 
  
但是, 用户必须确保在安装提供程序之前启用了 .osc。
  
第三方 (包括 .osc 提供程序) 无法重新发布 .osc。 但是, 如果未安装 .osc, 则提供程序安装程序可以使用适当的 g 链接在客户端计算机上安装 .osc。 g-链接是中https://g.live.com的专门构造的 URL, 可将用户转发到相应的网页以下载 .osc。 .osc g 链接的格式为https://g.live.com/0CR _lcid_/ _Glink_, 其中_LCID_和_Glink_指定客户端计算机上的 Outlook 的区域设置、版本和位数。 每个 g 链接指向一个可执行文件, 并特定于指定的_LCID_和_Glink_值。 
  
例如, 将最新版本的 .osc for outlook 2003 或 outlook 2007 for LCID 1033 (美国英语) 的 g-链接安装如下:
  
https://g.live.com/0CR1033/80
  
有关 Outlook 的不同版本和位数以及受支持的区域设置的_LCID_值的详细信息, 请参阅下面的[安装清单](#olosc_InstallationOverview_InstallationChecklist)一节中的 #7 _Glink_ 。 

<a name="olosc_InstallationOverview_InstallationChecklist"> </a>

## <a name="installation-checklist"></a>安装清单

提供程序安装程序包应执行一系列安装检查 (如图1中所示), 以确保提供程序成功安装。
  
**图1。提供程序安装逻辑**

![安装清单](media/odc_ol14_ta_OSC_Fig07.gif)
  
以下过程介绍了图1中概述的安装检查。
  
1. 作为先决条件, 请检测 outlook 是否已安装或存在, 如果已安装或存在, 则确定 outlook 版本是否支持 .osc。 有关检测已安装的 outlook 版本的详细信息, 请参阅[检查 outlook 的版本](https://msdn.microsoft.com/library/672fc380-a29b-4e99-9211-949fd5065723%28Office.15%29.aspx)。
    
   - 如果安装的 outlook 版本早于 outlook 2003, 则提供程序安装过程将无法完成。 通知用户在继续安装 .osc 提供程序之前, 先获取受支持的 Outlook 和 .osc 版本。
    
   - 如果未安装 Outlook, 请继续执行步骤2。
    
   - 如果安装了 outlook 2003 或 outlook 2007, 请继续执行步骤3。 
    
   - 如果安装了 outlook 2010 或 outlook 2013, 请继续执行步骤4。
    
2. **如果客户端计算机上未安装 Outlook, 请继续执行此步骤:**
    
   1. 检查是否已将 .osc 安装为 Outlook 2010 或 outlook 2013 的即点即用安装的默认组件。 检查 Windows `VirtualOutlook`注册表中以下位置中的项: 
      
      - 对于 Outlook 2010,`HKEY_LOCAL_MACHINE\Software\Microsoft\Office\14.0\Common\InstallRoot\Virtual\VirtualOutlook`
      
      - 对于 Outlook Social Connector 2013,`HKEY_LOCAL_MACHINE\Software\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook`
      
      `VirtualOutlook`键是一个 REG_SZ 值, 它包含已安装产品的区域设置标记, 如 "en-us"。 
      
   2. 如果`VirtualOutlook`该项不存在, 则客户端计算机上不存在 Outlook, 并且提供程序安装过程无法完成。 通知用户在继续安装 .osc 提供程序之前, 先获取受支持的 Outlook 和 .osc 版本。 
      
   3. 如果`VirtualOutlook`该项确实存在, 则通过客户端计算机上的即点即用来传递 Outlook。 通过检查 Windows 注册表中以下位置中的项, `OSCVersion`继续检查已安装的 .osc 类型库的版本: 
      
      `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\OSCVersion`
      
      的值`OSCVersion`是一个字符串, 它指定类型库 Socialprovider 的版本编号 (例如, "1.0"、"1.1" 或 "15")。 
      
   4. 如果`OSCVersion`是 "1.0"、"1.1" 或 "15", 则安装了适当版本的 .osc。 继续执行步骤6以查找当前的 Outlook 用户界面区域设置, 以准备安装最新版本的 .osc。 
      
   5. 否则, `OSCVersion`不包含预期值。 继续执行步骤6以查找当前 Outlook 用户界面区域设置, 以准备安装适当版本的 .osc。 
    
3. **如果客户端计算机上安装了 outlook 2003 或 outlook 2007, 请继续执行此步骤:**
    
   1. 通过编写安装程序自定义操作来验证 .osc 是否已安装, 以测试是否存在以下限定的组件 ID:
      
      `{A3B82DA3-8AD9-4935-AEA8-54B754459483}`
      
      限定的组件 ID 是提供单层间接寻址方法的 GUID, 类似于指针。 有关 windows installer 的详细信息, 请参阅[windows installer 文档的路线图](https://docs.microsoft.com/windows/desktop/msi/roadmap-to-windows-installer-documentation)。
      
   2. 如果指定的限定组件存在, 则会安装某个版本的 .osc。 继续执行步骤5以查找当前的 Outlook 用户界面区域设置, 以准备安装最新版本的 .osc。
      
   3. 否则, 将不会安装 .osc。 继续执行步骤6以查找当前 Outlook 用户界面区域设置, 以准备安装适当版本的 .osc。
      
4. **如果客户端计算机上安装了 outlook 2010 或 outlook 2013, 请继续执行此步骤:**
    
   1. 通过检查 Windows 注册表中以下位置中的`Bitness`项来确定已安装的 Outlook 版本的位数: 
      
      - 对于 Outlook 2010, 请查看`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\14.0\Outlook`
      
      - 对于 Outlook 2013, 请查看`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Outlook`
      
      对于`Bitness` 32 位 outlook, 此项为 "x86", 对于64位 outlook 为 "x64"。 
      
   2. 如果提供程序是托管提供程序, 并且您已将提供程序组件指定为 "**任何 CPU**" 的目标平台, 请继续执行步骤6以查找当前 Outlook 用户界面区域设置, 以准备安装最新版本的 .osc。 提供程序将在32位和64位版本的 .osc 上运行。
      
   3. 如果提供程序是本机 COM 组件, 请检查已安装的 Outlook 版本的位数:
      
      - 如果安装的 Outlook 版本是32位, 则安装过程将需要安装32位提供程序 (在步骤8中), 然后再确保安装了适当的 .osc。
      
      - 否则, 已安装的 Outlook 版本为64位, 安装过程将必须安装64位提供程序 (在步骤8中), 然后才能确保安装了适当的 .osc。 
      
   4. 继续执行步骤6以查找当前 Outlook 用户界面区域设置, 以准备安装适当版本的 .osc。
    
5. **如果安装了 outlook 2003 或 outlook 2007, 并且在客户端计算机上安装了 .osc, 请继续执行此步骤:** 检查 Windows 注册表中以下位置的`OSCLcid`键, 以检查当前 Outlook 用户界面区域设置: 
    
   `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\OSCLcid`
    
   `OSCLcid` key 是一个 DWORD 值, 它指定表示当前 Outlook 用户界面区域设置的 Internet 工程任务组 (IETF) 区域设置标记 (由[[RFC4646]](https://www.ietf.org/rfc/rfc4646.txt)和[[RFC4647]](https://www.ietf.org/rfc/rfc4647.txt)定义)。 继续执行第7步, 以在客户端计算机上安装最新的 .osc。
    
6. **如果安装了 outlook 2003 或 outlook 2007, 或者 outlook 2010 或 outlook 2013 存在, 则继续执行此步骤, 但不一定要在客户端计算机上安装最新的 .osc:**
    
   使用**LanguageSettings**对象来确定 Outlook 用户界面区域设置的 LCID。 下面的 Visual Basic 脚本编写版 (VBScript) 代码段演示如何获取 Outlook 用户界面区域设置的 LCID。 
    
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

7. **如果安装程序具有已安装的 Outlook 版本的 LCID, 但不一定要在客户端计算机上安装最新的 .osc, 请继续执行此步骤:**
    
   将 g 链接链接到安装包, 以确保客户端计算机上安装了最新版本的 .osc。 g 链接格式如下所示:
    
   https://g.live.com/0CR_LCID_/  _Glink_
    
   有关支持的_LCID_值, 请参阅下面的表1和表2以获得支持的_Glink_值。 例如, 将最新版本的32位 .osc 安装为32位 Outlook Social Connector 2013 (美国英语) 的 g-链接如下所示: 
    
   https://g.live.com/0CR1033/82
    
8. 安装提供程序。 提供程序安装过程必须在相应的 Windows 注册表位置中注册编程标识符 (ProgID)。 有关详细信息, 请参阅[注册提供程序](registering-a-provider.md)。 此外, 请确保要安装的提供程序的位数与客户端计算机上存在的 Outlook 版本的位数相同。 例如, 如果存在32位 outlook 2013, 则安装32位提供程序, 如果安装了64位 outlook 2013, 则为64位提供程序。 对于 Outlook 2003 或 2007, 仅适用于32位版本的提供程序。 
    
**表 1: 针对 .osc 的十六进制支持的区域设置和对应的 LCID 值**
  
|**位置**|**LCID**|
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
|cyrl-cs  <br/> |3098  <br/> |
|即将-cs  <br/> |2074  <br/> |
|sv-se  <br/> |1053  <br/> |
|th-th  <br/> |1054  <br/> |
|tr-tr  <br/> |1055  <br/> |
|uk-ua  <br/> |1058  <br/> |
|zh-cn  <br/> |2052  <br/> |
|zh-tw  <br/> |1028  <br/> |
   
**表 2: 受支持的 .osc Glink 值**
  
|**Glink 值**|**Function**|
|:-----|:-----|
|80  <br/> |安装适用于 outlook 2003 或 outlook 2007 的最新版本的 .osc。  <br/> |
|82  <br/> |安装适用于 Outlook 2007、outlook 2010 或 outlook Social Connector 2013 的32位 .osc 的最新修补程序。  <br/> |
|83  <br/> |安装适用于 Outlook 2010 或 outlook Social Connector 2013 的64位 .osc 的最新修补程序。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [注册提供程序](registering-a-provider.md) 
- [学习开发提供程序的快速步骤](quick-steps-for-learning-to-develop-a-provider.md)
- [部署提供程序](deploying-a-provider.md)

