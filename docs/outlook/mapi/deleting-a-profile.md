---
title: 删除配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4d01ab2e-40fd-409d-a69d-163b7d5462ca
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1cd87b92a9d289f06e466f4e44ce757c93074336
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410201"
---
# <a name="deleting-a-profile"></a>删除配置文件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **删除配置文件**
  
- 调用 [IProfAdmin：:D eleteProfile](iprofadmin-deleteprofile.md)。
    
 **DeleteProfile** 将配置文件标记为待删除（如果当前正在使用，则等待配置文件不再处于活动状态才能删除它）。 配置文件实际上不会消失，直到每个具有活动会话的客户端断开连接。 
  
 **DeleteProfile** 调用配置文件中每个邮件服务的入口点函数  _，ulContext_ 参数设置为 MSG_SERVICE_DELETE。 在从配置文件中实际删除服务之前，将调用入口点函数。 
  

