---
title: 邮件存储中的特殊文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9462070e-1472-4e12-ba4e-e4ac60022892
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ae881f56695914627e8c2f6f61f143da91cd78a8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416760"
---
# <a name="special-folders-in-message-stores"></a>邮件存储中的特殊文件夹

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
可能会提前创建特殊文件夹，如收件箱、发件箱和搜索结果文件夹，并受邮件存储提供程序保护。 如果文件夹不存在，MAPI 将尝试通过调用 [HrValidateIPMSubtree](hrvalidateipmsubtree.md) 函数在邮件存储中创建它们。 有关详细信息，请参阅 [MAPI 特殊文件夹](mapi-special-folders.md)。
  
## <a name="see-also"></a>另请参阅



[实现邮件存储中的文件夹](implementing-folders-in-message-stores.md)

