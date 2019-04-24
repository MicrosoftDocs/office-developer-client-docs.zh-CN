---
title: 邮件存储区中的特殊文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9462070e-1472-4e12-ba4e-e4ac60022892
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ae881f56695914627e8c2f6f61f143da91cd78a8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344441"
---
# <a name="special-folders-in-message-stores"></a>邮件存储区中的特殊文件夹

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
"收件箱"、"发件箱" 和 "搜索结果" 文件夹等特殊文件夹可以提前创建并受邮件存储提供程序保护。 如果文件夹不存在, MAPI 将尝试通过调用[HrValidateIPMSubtree](hrvalidateipmsubtree.md)函数在邮件存储区中创建这些文件夹。 有关详细信息, 请参阅[MAPI 特殊文件夹](mapi-special-folders.md)。
  
## <a name="see-also"></a>另请参阅



[实现邮件存储中的文件夹](implementing-folders-in-message-stores.md)

