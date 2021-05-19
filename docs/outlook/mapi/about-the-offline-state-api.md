---
title: 关于脱机状态 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 18b0d284-c224-a022-47d9-b2d82a32f996
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: 56793ae0d2c2ce76c89c7cda4985618e3a40ccfd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410481"
---
# <a name="about-the-offline-state-api"></a>关于脱机状态 API

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
脱机状态 API 支持指示 Microsoft Outlook 2013 和 Microsoft Outlook 2010 中用户连接状态更改的回调，例如，从 Outlook 2013 或 Outlook 2010 联机到脱机。 API 在 2013 或 Outlook 2010 Outlook全局脱机对象来跟踪给定用户帐户配置文件的此类更改。 通知是唯一受支持的回调形式。 作为此 API 的客户端，希望收到此类连接状态更改通知的邮件提供商执行以下操作：
  
1. 实现 **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**。 
    
2. 使用 **[HrOpenOfflineObj](hropenofflineobj.md)** 打开特定配置文件的现有脱机对象。 
    
3. 确定对象是否具有使用 **[IMAPIOffline：：GetCapabilities](imapioffline-getcapabilities.md)** 提供联机或脱机通知的功能。 
    
4. 使用 **[IMAPIOfflineMgr：：Advise](imapiofflinemgr-advise.md)** 注册用于联机或脱机通知的对象。 邮件提供商现在可以使用 **IMAPIOfflineNotify** 接收 2013 Outlook 2010 Outlook 2010 发送的通知。 
    
5. 关闭时，使用 **[IMAPIOfflineMgr：：Unadvise](imapiofflinemgr-unadvise.md)** 删除联机和脱机通知的注册。 
    
> [!NOTE]
> 通常，Outlook 2013 和 Outlook 2010 可以通知客户端联机/脱机更改以及其他更改，但脱机状态 API 仅支持联机/脱机更改通知。 客户端应忽略所有其他通知。 有关详细信息，请参阅 **[IMAPIOfflineNotify：：Notify](imapiofflinenotify-notify.md)** and **[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)**。 
  
 有关使用脱机状态 API 的客户端示例，请参阅关于示例 [脱机状态加载项](about-the-sample-offline-state-add-in.md)。 示例脱机状态加载项是一个 COM 加载项，它使用脱机状态 API 监视和更改连接状态。
  
此 API 提供以下内容：
  
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
    

