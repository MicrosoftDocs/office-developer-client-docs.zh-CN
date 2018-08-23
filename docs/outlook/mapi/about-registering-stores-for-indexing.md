---
title: 关于注册用于建立索引的存储区
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: dd2aa06a-96e8-1291-18b5-fc3c40b74e4d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 195812f53c4c0aaf20e4ed6e215d15b0295c9a07
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584182"
---
# <a name="about-registering-stores-for-indexing"></a>关于注册用于建立索引的存储区

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
本主题是特定于 Microsoft Office Outlook 2007 中的即时搜索。
  
即时搜索允许您快速查找在 Outlook 中的项目。 它使用 Windows 桌面搜索的组件。
  
MAPI 协议处理程序检查 Windows 注册表中以便它应该索引搜索目的的存储。 想要编制索引的存储提供程序必须在 Windows 注册表中注册。
  
默认情况下，Windows 桌面搜索将以下四种存储提供程序添加到 Windows 注册表以允许索引：
  
- 存储个人文件夹文件 (。PST)。
    
-  Microsoft Exchange 存储中，包括任何脱机文件夹文件 (.ost)。 
    
-  公用文件夹存储区。 
    
-  Microsoft Office Outlook Connector for MSN 存储区。 
    
 想要编制索引的第三方存储提供程序必须在 Windows 注册表中进行注册。 
  
> [!NOTE]
> 管理员和用户可以使用组策略设置阻止 Windows 桌面搜索索引 Outlook 项目。 有关详细信息，请参阅[扩展 Windows 桌面搜索](http://msdn.microsoft.com/library/2eab146a-8516-4b95-b73c-ca7f980ba233%28Office.15%29.aspx)。 
  
## <a name="registry-keys"></a>注册表项

计算机上，要编制索引的所有存储提供程序必须只有一个 Windows 注册表中的以下三个注册表项下都注册。 每个按以下顺序这些项下查找 MAPI 协议处理程序：
  
1. [HKLM] \Software\Policies\Microsoft\Windows\Windows Search\
    
2. [HKLM] \Software\Microsoft\Windows\Windows Search\Preferences\
    
3. [HKCU] \Software\Microsoft\Windows\Windows Search\Preferences\
    
 每个注册表项下的值对应于将编制索引的存储提供程序。 全局唯一标识符 (GUID) 的存储提供程序，其中的类型为**DWORD**具有 0x00000001 的十六进制值的值的名称。 
  
## <a name="guids-for-store-providers"></a>存储提供程序的 Guid

MAPI 属性**[PR_MDB_PROVIDER](pidtagstoreprovider-canonical-property.md)** 指定的 MAPI 存储区的 GUID。 下表中描述了 Outlook 索引的存储提供程序的 Guid。 
  
||||
|:-----|:-----|:-----|
|**存储提供程序类型** <br/> |**GUID** <br/> |**备注** <br/> |
|个人文件夹文件 (。PST)  <br/> |{4154494E-BFF9-01B8-00AA-0037D96E0000}  <br/> |GUID 为**MSPST_UID_PROVIDER**述公共头文件 mspst.h <br/> |
|Exchange  <br/> |{C0A19454-7F29-1B10-A587-08002B2A2517}  <br/> |GUID 为**pbExchangeProviderPrimaryUserGuid**述公共头文件 edkmdb.h <br/> |
|公用文件夹  <br/> |{70fab278-f7af-cd11-9bc8-00aa002fc45a}  <br/> |GUID 为**pbExchangeProviderPublicGuid**述公共头文件 edkmdb.h <br/> |
|MSN 的 outlook Connector  <br/> |{c34f5c97-eb05-bb4b-b199-2a7570ec7cf9}  <br/> |无  <br/> |
   
## <a name="see-also"></a>另请参阅



[关于存储区 API](about-the-store-api.md)

