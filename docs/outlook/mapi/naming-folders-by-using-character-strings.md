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
# <a name="naming-folders-by-using-character-strings"></a><span data-ttu-id="0c2c5-103">使用字符字符串命名文件夹</span><span class="sxs-lookup"><span data-stu-id="0c2c5-103">Naming Folders by Using Character Strings</span></span>

  
  
<span data-ttu-id="0c2c5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0c2c5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0c2c5-105">如果您经常在会话期间访问一个或多个文件夹，请考虑使用[IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md)方法分配到的文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="0c2c5-105">If you access one or more folders frequently during a session, consider assigning names to the folders with the [IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md) method.</span></span> <span data-ttu-id="0c2c5-106">尽管**IMsgStore::SetReceiveFolder**主要用于建立要接收传入邮件的特定邮件类别的特殊文件夹，但它还可与名称相关联的任何文件夹。</span><span class="sxs-lookup"><span data-stu-id="0c2c5-106">Although **IMsgStore::SetReceiveFolder** is used primarily to establish special folders to receive incoming messages for particular message classes, it can also be used to associate any folder with a name.</span></span> <span data-ttu-id="0c2c5-107">名称可以是相同的邮件类，也可以是任意字符串，并为您的客户端使用自定义。</span><span class="sxs-lookup"><span data-stu-id="0c2c5-107">The name can be the same as the message class or it can be any character string, customized for your client's use.</span></span> <span data-ttu-id="0c2c5-108">与文件夹关联名称减少查找并打开该文件夹所需的时间。</span><span class="sxs-lookup"><span data-stu-id="0c2c5-108">Associating a name with a folder decreases the time it takes to find and open the folder.</span></span> 
  

