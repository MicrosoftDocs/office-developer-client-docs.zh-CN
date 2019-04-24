---
title: 关于脱机状态 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 18b0d284-c224-a022-47d9-b2d82a32f996
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: 56793ae0d2c2ce76c89c7cda4985618e3a40ccfd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321782"
---
# <a name="about-the-offline-state-api"></a>关于脱机状态 API

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
脱机状态 API 支持回调指示用户的连接状态在 microsoft outlook 2013 和 microsoft outlook 2010 中的更改, 例如, 在 outlook 2013 中联机或 outlook 2010 脱机。 API 在 outlook 2013 或 outlook 2010 中使用全局脱机对象跟踪给定用户帐户配置文件的此类更改。 通知是唯一受支持的回调形式。 作为此 API 的客户端, 希望通知这些连接状态更改的邮件提供程序将执行以下操作:
  
1. 实现**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**。 
    
2. 使用**[HrOpenOfflineObj](hropenofflineobj.md)** 打开特定配置文件的现有脱机对象。 
    
3. 确定对象是否具有使用**[IMAPIOffline:: GetCapabilities](imapioffline-getcapabilities.md)** 提供联机或脱机通知的功能。 
    
4. 使用**[IMAPIOfflineMgr:: 建议](imapiofflinemgr-advise.md)** 为联机通知或脱机通知注册对象。 邮件提供商现在可以使用**IMAPIOfflineNotify**接收 outlook 2013 或 outlook 2010 发送的通知。 
    
5. 关闭后, 请使用**[IMAPIOfflineMgr:: Unadvise](imapiofflinemgr-unadvise.md)** 删除联机和脱机通知的注册。 
    
> [!NOTE]
> 通常情况下, outlook 2013 和 outlook 2010 可以通知客户端的联机/脱机更改和其他更改, 但脱机状态 API 仅支持联机/脱机更改的通知。 客户端应忽略所有其他通知。 有关详细信息, 请参阅**[IMAPIOfflineNotify:: Notify](imapiofflinenotify-notify.md)** and **[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)**。 
  
 有关使用脱机状态 API 的客户端的示例, 请参阅[关于示例脱机状态加载项](about-the-sample-offline-state-add-in.md)。 示例脱机状态外接程序是一个 COM 加载项, 它使用脱机状态 API 监视和更改连接状态。
  
此 API 提供以下内容:
  
定义：
  
- [MAPI 常量](mapi-constants.md)
    
数据类型:
  
- **[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)**
    
- **[MAPIOFFLINE_CALLBACK_TYPE](mapioffline_callback_type.md)**
    
- **[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)**
    
函数：
  
- **[HrOpenOfflineObj](hropenofflineobj.md)**
    
接口：
  
- **[IMAPIOffline](imapiofflineiunknown.md)**
    
- **[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)**
    
- **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**
    

