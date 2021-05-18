---
title: 关于注册用于索引的存储区
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
# <a name="about-registering-stores-for-indexing"></a>关于注册用于索引的存储区

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本主题特定于 Microsoft Office Outlook 2007 中的即时搜索。
  
通过即时搜索，可以快速查找Outlook。 它使用桌面Windows的组件。
  
MAPI 协议处理程序Windows注册表中查找出于搜索目的应编制索引的存储区。 必须在注册表中注册要编制索引Windows提供程序。
  
默认情况下，Windows搜索将以下四种类型的存储提供程序添加到Windows注册表中以允许编制索引：
  
- 个人文件夹文件存储 (。PST) 。
    
-  Microsoft Exchange存储，包括任何脱机文件夹 (.ost) 。 
    
-  公用文件夹的存储区。 
    
-  适用于 MSN Microsoft Office Outlook连接器存储。 
    
 要编制索引的第三方存储提供程序必须在注册表中Windows自身。 
  
> [!NOTE]
> 管理员和用户可以使用组策略设置来Windows桌面搜索对项目编制Outlook索引。 有关详细信息，请参阅扩展Windows[桌面搜索。](https://msdn.microsoft.com/library/2eab146a-8516-4b95-b73c-ca7f980ba233%28Office.15%29.aspx) 
  
## <a name="registry-keys"></a>注册表项

在计算机上，所有要编制索引的存储区提供程序都必须在注册表中的以下三个注册表项之一Windows注册。 MAPI 协议处理程序按以下顺序查看其中每个键：
  
1. [HKLM]\Software\Policies\Microsoft\Windows\Windows Search\
    
2. [HKLM]\Software\Microsoft\Windows\Windows Search\Preferences\
    
3. [HKCU]\Software\Microsoft\Windows\Windows Search\Preferences\
    
 键下的每个值对应于将编制索引的存储区提供程序。 值的名称是存储提供程序的全局唯一标识符 (GUID) ，其类型为 **DWORD，** 并且具有十六进制值0x00000001。 
  
## <a name="guids-for-store-providers"></a>存储提供程序的 GUID

MAPI 属性 **[PR_MDB_PROVIDER](pidtagstoreprovider-canonical-property.md)** 指定 MAPI 存储的 GUID。 下表介绍了存储提供程序的 GUID Outlook索引的 GUID。 
  
||||
|:-----|:-----|:-----|
|**存储提供程序的类型** <br/> |**GUID** <br/> |**备注** <br/> |
|个人文件夹文件 (。PST)   <br/> |{4154494E-BFF9-01B8-00AA-0037D96E0000}  <br/> |GUID 作为文档记录在公共头文件 mspst.h **中MSPST_UID_PROVIDER** <br/> |
|Exchange  <br/> |{C0A19454-7F29-1B10-A587-08002B2A2517}  <br/> |GUID 在公共头文件 edkmdb.h 中记录为 **pbExchangeProviderPrimaryUserGuid** <br/> |
|公用文件夹  <br/> |{70fab278-f7af-cd11-9bc8-00aa002fc45a}  <br/> |GUID 在公共头文件 edkmdb.h 中记录为 **pbExchangeProviderPublicGuid** <br/> |
|OutlookMSN 连接器  <br/> |{c34f5c97-eb05-bb4b-b199-2a7570ec7cf9}  <br/> |无  <br/> |
   
## <a name="see-also"></a>另请参阅



[关于存储 API](about-the-store-api.md)

