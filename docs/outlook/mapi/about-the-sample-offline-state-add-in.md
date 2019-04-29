---
title: 关于示例脱机状态加载项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: a6bdf408-114a-2203-189f-101251a65a8c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bf8e647af4aba53dfc24880e6ff491985b50a613
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431181"
---
# <a name="about-the-sample-offline-state-add-in"></a>关于示例脱机状态加载项

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
脱机状态 API 支持回调指示用户在 outlook 中的连接状态发生更改, 例如, 在 outlook 中联机为脱机。 示例脱机状态外接程序是用 c + + 编写的 COM 加载项, 它演示如何接收连接状态更改的通知, 以及如何使用脱机状态 API 修改当前状态。 有关脱机状态 API 的详细信息，请参阅[关于脱机状态 API](about-the-offline-state-api.md)。
  
## <a name="in-this-section"></a>本节内容

- [安装示例脱机状态加载项](installing-the-sample-offline-state-add-in.md)
    
- 介绍如何下载和安装示例脱机状态加载项。
    
- [设置脱机状态加载项](setting-up-an-offline-state-add-in.md)
    
- 介绍如何实现连接、初始化和安装程序功能, 以便使用脱机状态外接程序。
    
- [使用脱机状态加载项监视连接状态更改](monitoring-connection-state-changes-using-an-offline-state-add-in.md)
    
- 介绍如何使用**[HrOpenOfflineObj](hropenofflineobj.md)** 函数获取脱机对象, 以监视和更改连接状态。 
    
- [断开与脱机状态外接程序的连接](disconnecting-an-offline-state-add-in.md)
    
- 介绍如何在外接程序断开连接时正确终止和清理脱机状态外接程序。
    
## <a name="see-also"></a>另请参阅



[关于脱机状态 API](about-the-offline-state-api.md)

