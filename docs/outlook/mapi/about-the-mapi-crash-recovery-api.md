---
title: 关于 MAPI 故障恢复 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: bc1e1f55-1959-a4a9-a24d-f006af531c9a
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: 1acca6d806c1734007ac7c5e41059d3a870dc5bb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420260"
---
# <a name="about-the-mapi-crash-recovery-api"></a>关于 MAPI 故障恢复 API

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 故障恢复 API 检查个人文件夹文件 (PST) 或脱机文件夹文件 (OST) 共享内存的状态，以验证数据是否处于一致状态。 如果状态一致 [，MAPICrashRecovery](mapicrashrecovery.md) 函数会将数据从打开的 PST 或 OST 移动到磁盘，并锁定 PST 或 OST，并且不允许对数据进行任何读或写访问。 这将确保数据保持一致状态，直到进程终止。 通过确保在终止进程之前，PST 或 OST 保持一致状态，可以防止 Microsoft Outlook 2013 和 Microsoft Outlook 2010 显示以下错误消息，并避免性能问题。 
  
 **上次使用数据文件时未正确关闭，并且正在检查是否出现问题。正在进行检查时，性能可能会受到影响。**
  
此 API 提供以下内容：
  
常量：
  
- [MAPI 常量](mapi-constants.md)
    
函数：
  
- [MAPICrashRecovery](mapicrashrecovery.md)
    
## <a name="see-also"></a>另请参阅



[使用 MAPI 故障恢复 API](how-to-use-the-mapi-crash-recovery-api.md)

