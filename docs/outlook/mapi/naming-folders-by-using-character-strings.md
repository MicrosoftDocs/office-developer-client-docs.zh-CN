---
title: 使用字符字符串命名文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ec3c023b-7c99-489c-8217-78b303dc10df
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a6ea37bf573dab996b5a8fd7886a76fddd5b98ff
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776531"
---
# <a name="naming-folders-by-using-character-strings"></a>使用字符字符串命名文件夹

  
  
**适用于**： Outlook 
  
如果您经常在会话期间访问一个或多个文件夹，请考虑使用[IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md)方法分配到的文件夹的名称。 尽管**IMsgStore::SetReceiveFolder**主要用于建立要接收传入邮件的特定邮件类别的特殊文件夹，但它还可与名称相关联的任何文件夹。 名称可以是相同的邮件类，也可以是任意字符串，并为您的客户端使用自定义。 与文件夹关联名称减少查找并打开该文件夹所需的时间。 
  

