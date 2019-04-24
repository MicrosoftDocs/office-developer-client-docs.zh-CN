---
title: 安装 MAPI 子系统
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
api_type:
- COM
ms.assetid: 29fb4c44-1a59-457e-813b-a982bd72891c
description: 上次修改时间：2015 年 3 月 9 日
localization_priority: Priority
ms.openlocfilehash: 112a683f5967f8740c2d21285eb4ebbc0f455c48
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309637"
---
# <a name="installing-the-mapi-subsystem"></a>安装 MAPI 子系统

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
受支持的 Windows 版本将 MAPI 存根库 Mapi32.dll 安装在 _\<drive\>_ \Windows\System32 文件夹中。 
  
受支持的 Windows 版本如下所示：
  
- Windows 7。
    
- Windows Vista。
    
- Windows Server 2008。
    
- Windows Server 2003。
    
- Windows XP。
    
若要正确安装 MAPI 系统，请安装包含基于 MAPI 子系统的应用程序，如 Microsoft Outlook。
  
可以在系统注册表中找到与计算机的 MAPI 子系统相关的信息。 注册表项中的所有值均为字符字符串。 
  
邮件服务安装程序负责在以下系统注册表项中创建安装信息： 
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Messaging Subsystem`
  
邮件服务必须向系统注册表中添加注册表项。 
  
下表简要介绍了客户端如何检索其计算机上的 MAPI 子系统的版本信息。
  
|**检查**|**注册表**|
|:-----|:-----|
|MAPI 可用性  <br/> |查找 `MAPIX=1`。  <br/> |
|可用的 MAPI 版本  <br/> |查找“_x.x.x_”形式的 MAPIXVER 字符串。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 编程概述](mapi-programming-overview.md)

