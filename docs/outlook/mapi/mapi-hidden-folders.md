---
title: MAPI 隐藏文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8b3b9c80-f7f4-4f37-bd6b-323469d020f1
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9f9daa2169a087cf962d09a7c135e2829c7cd1ee
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424243"
---
# <a name="mapi-hidden-folders"></a>MAPI 隐藏文件夹

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
隐藏文件夹是客户端在邮件存储区的根文件夹中创建的通用文件夹, 而不是在人际邮件 (IPM) 子树的根文件夹中创建的文件夹。 由于这些文件夹不放置在 IPM 子树中, 因此邮件存储提供程序通常会将这些文件夹隐藏在用户的视图中。 隐藏的文件夹通常包含与邮件存储区相关但与用户无关的信息。 客户端创建用于存储的隐藏文件夹, 例如, 与文件夹层次结构的其余部分一起保存的附加信息。
  
MAPI 要求所有客户端都能够显示、创建、修改和删除 IPM 子树中的文件夹。 对在其他树中使用文件夹的支持被认为是可选的。 但是, 所有可用作默认存储的邮件存储以及可以发送和接收邮件的所有邮件都应完全支持隐藏文件夹。
  
## <a name="see-also"></a>另请参阅



[MAPI 文件夹](mapi-folders.md)

