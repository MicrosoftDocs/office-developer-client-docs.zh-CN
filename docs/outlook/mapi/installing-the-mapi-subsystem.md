---
title: 安装 MAPI 子系统
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 29fb4c44-1a59-457e-813b-a982bd72891c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: adb4d09ccce95683ac46e7b271fafa328b1a9f97
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575348"
---
# <a name="installing-the-mapi-subsystem"></a>安装 MAPI 子系统

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
受支持的版本的 Windows 中安装的 MAPI 存根库 Mapi32.dll，_\<驱动器\>_ \Windows\System32 文件夹。 
  
支持的 Windows 版本如下所示：
  
- Windows 7。
    
- Windows Vista。
    
- Windows Server 2008。
    
- Windows Server 2003。
    
- Windows XP。
    
若要正确安装 MAPI 子系统，安装包含基于 MAPI 的子系统，如 Microsoft Outlook 的应用程序。
  
您可以在系统注册表中找到有关计算机的 MAPI 子系统安装的信息。 注册表项中的所有值都的字符串。 
  
消息服务安装程序负责在以下系统注册表项中创建了安装信息： 
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Messaging Subsystem`
  
消息服务必须添加到系统注册表项。 
  
下表总结了客户端如何检索 MAPI 子系统在其计算机上的版本信息。
  
|**若要检查**|**Registry**|
|:-----|:-----|
|MAPI 的可用性  <br/> |查找`MAPIX=1`。  <br/> |
|可用版本的 MAPI  <br/> |查找窗体" _x.x.x_"MAPIXVER 字符串。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 编程概述](mapi-programming-overview.md)

