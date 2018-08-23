---
title: 关于脱机状态 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 18b0d284-c224-a022-47d9-b2d82a32f996
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: aa30a173251193d74d6560c8dce2663463a18e36
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565982"
---
# <a name="about-the-offline-state-api"></a>关于脱机状态 API

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
脱机状态 API 支持指示 Microsoft Outlook 2013 和 Microsoft Outlook 2010 中的用户的连接状态的变化的回调 — 例如，从要在 Outlook 2013 或 Outlook 2010 中的联机到脱机。 API 使用 Outlook 2013 或 Outlook 2010 中的全局脱机对象来跟踪此更改为给定的用户帐户配置文件。 通知是回调的唯一受支持的设备。 此 api 的客户端，为邮件提供商希望此类连接状态更改通知执行以下操作：
  
1. 实现**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**。 
    
2. 打开现有脱机使用**[HrOpenOfflineObj](hropenofflineobj.md)** 特定配置文件对象。 
    
3. 确定对象是否有能力提供联机或脱机使用**[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)** 的通知。 
    
4. 注册使用**[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)** 联机或脱机通知的对象。 邮件提供商现在可以接收通知 Outlook 2013 或 Outlook 2010 发送使用**IMAPIOfflineNotify**。 
    
5. 在关闭，删除注册联机和脱机使用**[IMAPIOfflineMgr::Unadvise](imapiofflinemgr-unadvise.md)** 的通知。 
    
> [!NOTE]
> 一般情况下，Outlook 2013 和 Outlook 2010，则可以向联机/脱机的更改以及其他更改，客户端的通知，但脱机状态 API 支持仅通知联机/脱机的更改。 客户端应忽略所有其他通知。 有关详细信息，请参阅**[IMAPIOfflineNotify::Notify](imapiofflinenotify-notify.md)** 和**[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)**。 
  
 有关使用脱机状态 API 的客户端的示例，请参阅[有关示例脱机状态外接程序](about-the-sample-offline-state-add-in.md)。 示例脱机状态加载项是使用脱机状态 API 来监控并更改连接状态的 COM 加载项。
  
此 API 提供下列功能：
  
定义：
  
- [MAPI 常量](mapi-constants.md)
    
数据类型：
  
- **[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)**
    
- **[MAPIOFFLINE_CALLBACK_TYPE](mapioffline_callback_type.md)**
    
- **[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)**
    
函数：
  
- **[HrOpenOfflineObj](hropenofflineobj.md)**
    
接口：
  
- **[IMAPIOffline](imapiofflineiunknown.md)**
    
- **[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)**
    
- **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**
    

