---
title: 关于注册用于编制索引的存储
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: dd2aa06a-96e8-1291-18b5-fc3c40b74e4d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 96322d12b3b7b334b5f78f81910dcf34c3fc78e1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321824"
---
# <a name="about-registering-stores-for-indexing"></a>关于注册用于编制索引的存储

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本主题特定于 Microsoft Office Outlook 2007 中的 "即时搜索"。
  
即时搜索允许您在 Outlook 中快速查找项目。 它使用 Windows 桌面搜索的组件。
  
MAPI 协议处理程序将检查 Windows 注册表, 以查找它应为搜索而编制索引的存储。 必须在 Windows 注册表中注册要编制索引的存储提供程序。
  
默认情况下, windows Desktop Search 将以下四种类型的存储提供程序添加到 Windows 注册表中, 以允许进行索引:
  
- 存储个人文件夹文件 (。PST)。
    
-  Microsoft Exchange 存储, 包括任何脱机文件夹文件 (.ost)。 
    
-  公用文件夹的存储。 
    
-  microsoft Office Outlook Connector for MSN 的存储。 
    
 要编制索引的第三方存储提供程序必须在 Windows 注册表中注册自己。 
  
> [!NOTE]
> 管理员和用户可以使用组策略设置阻止 Windows Desktop Search 对 Outlook 项目编制索引。 有关详细信息, 请参阅[扩展 Windows 桌面搜索](https://msdn.microsoft.com/library/2eab146a-8516-4b95-b73c-ca7f980ba233%28Office.15%29.aspx)。 
  
## <a name="registry-keys"></a>注册表项

在计算机上, 要编制索引的所有存储提供程序都必须在 Windows 注册表中的以下三个注册表项中仅注册一个。 MAPI 协议处理程序将按以下顺序在其中的每个注册表项下查找:
  
1. [hklm\] \Software\Policies\Microsoft\Windows\Windows Search \
    
2. [hklm\] \Software\Microsoft\Windows\Windows Search\Preferences\
    
3. [HKCU] \Software\Microsoft\Windows\Windows Search\Preferences\
    
 键下的每个值都对应于要编制索引的存储提供程序。 值的名称是存储提供程序的全局唯一标识符 (GUID), 它的类型为**DWORD** , 且具有十六进制值0x00000001。 
  
## <a name="guids-for-store-providers"></a>存储提供程序的 guid

mapi 属性**[PR_MDB_PROVIDER](pidtagstoreprovider-canonical-property.md)** 指定 mapi 存储的 GUID。 下表描述了适用于 Outlook 索引的存储提供程序的 guid。 
  
||||
|:-----|:-----|:-----|
|**存储提供程序的类型** <br/> |**GUID** <br/> |**Notes** <br/> |
|个人文件夹文件 (。.pst  <br/> |{4154494E-BFF9-01B8-00AA-0037D96E0000}  <br/> |GUID 在公用头文件 mspst 中记录为**MSPST_UID_PROVIDER** <br/> |
|Exchange  <br/> |{C0A19454-7F29-1B10-A587-08002B2A2517}  <br/> |GUID 在公用头文件 edkmdb 中记录为**pbExchangeProviderPrimaryUserGuid** <br/> |
|公用文件夹  <br/> |{70fab278-f7af-cd11-9bc8-00aa002fc45a}  <br/> |GUID 在公用头文件 edkmdb 中记录为**pbExchangeProviderPublicGuid** <br/> |
|Outlook Connector for MSN  <br/> |{c34f5c97-eb05-bb4b-b199-2a7570ec7cf9}  <br/> |无  <br/> |
   
## <a name="see-also"></a>另请参阅



[关于存储 API](about-the-store-api.md)

