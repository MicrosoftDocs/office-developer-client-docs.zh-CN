---
title: 关于 MAPI 崩溃恢复 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: bc1e1f55-1959-a4a9-a24d-f006af531c9a
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: fbb6d22414daf3464e80fbf1d9cf92ccb3d560e3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576587"
---
# <a name="about-the-mapi-crash-recovery-api"></a>关于 MAPI 崩溃恢复 API

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 崩溃恢复 API 检查个人文件夹文件 (PST) 或脱机文件夹 (OST) 文件的状态共享内存来验证数据处于一致状态。 如果是处于一致状态，则会将数据从打开的 Pst 或 Ost 移到磁盘上锁定 Pst 或 Ost [MAPICrashRecovery](mapicrashrecovery.md)函数并将其不允许任何读取或写入访问数据。 这样可确保终止过程之前的数据保持一致状态。 通过确保 Pst 或 Ost 处于一致状态终止过程之前，您可以禁止 Microsoft Outlook 2013 和 Microsoft Outlook 2010 中显示以下错误消息，并避免性能问题。 
  
 **数据文件未无法正确关闭问题上次用，并且正在签。正在检查时，可能会影响性能。**
  
此 API 提供下列功能：
  
常量：
  
- [MAPI 常量](mapi-constants.md)
    
函数：
  
- [MAPICrashRecovery](mapicrashrecovery.md)
    
## <a name="see-also"></a>另请参阅



[使用 MAPI 崩溃恢复 API](how-to-use-the-mapi-crash-recovery-api.md)

