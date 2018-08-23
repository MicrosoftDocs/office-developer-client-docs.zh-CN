---
title: 邮件存储区中的特殊文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9462070e-1472-4e12-ba4e-e4ac60022892
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a5446ce30812b30b193e87484a7322d9ddf7d781
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572709"
---
# <a name="special-folders-in-message-stores"></a>邮件存储区中的特殊文件夹

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
可能提前创建如收件箱、 发件箱和搜索结果文件夹的特殊文件夹，并将其受消息存储提供程序。 如果文件夹不存在，则 MAPI 将尝试通过调用[HrValidateIPMSubtree](hrvalidateipmsubtree.md)函数消息存储库中创建它们。 有关详细信息，请参阅[MAPI 特殊文件夹](mapi-special-folders.md)。
  
## <a name="see-also"></a>另请参阅



[实现邮件存储区中的文件夹](implementing-folders-in-message-stores.md)

