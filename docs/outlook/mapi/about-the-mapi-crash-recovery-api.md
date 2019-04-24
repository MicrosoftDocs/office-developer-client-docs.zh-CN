---
title: 关于 MAPI 故障恢复 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: bc1e1f55-1959-a4a9-a24d-f006af531c9a
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: 1acca6d806c1734007ac7c5e41059d3a870dc5bb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321803"
---
# <a name="about-the-mapi-crash-recovery-api"></a>关于 MAPI 故障恢复 API

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 故障恢复 API 检查个人文件夹文件 (PST) 或脱机文件夹文件 (OST) 共享内存的状态, 以验证数据是否处于一致状态。 如果处于 "一致" 状态, 则[MAPICrashRecovery](mapicrashrecovery.md)函数会将数据从打开的 pst 或 OSTs 移动到磁盘, 并锁定 pst 或 OSTs, 并且不允许对数据进行任何读取或写入访问。 这样可确保在进程终止之前, 数据保持一致状态。 通过确保 pst 或 OSTs 在进程终止之前处于一致状态, 您可以阻止 microsoft outlook 2013 和 microsoft outlook 2010 显示以下错误消息, 避免出现性能问题。 
  
 **上次使用数据文件时, 它未正确关闭, 且正在检查是否存在问题。在检查过程中, 性能可能会受到影响。**
  
此 API 提供以下内容:
  
称作
  
- [MAPI 常量](mapi-constants.md)
    
函数：
  
- [MAPICrashRecovery](mapicrashrecovery.md)
    
## <a name="see-also"></a>另请参阅



[使用 MAPI 故障恢复 API](how-to-use-the-mapi-crash-recovery-api.md)

