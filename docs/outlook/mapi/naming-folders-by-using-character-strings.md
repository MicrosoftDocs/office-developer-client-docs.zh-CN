---
title: 使用字符串命名文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ec3c023b-7c99-489c-8217-78b303dc10df
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 49ffe6b45002aec6660130132321559fc07c01c3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428310"
---
# <a name="naming-folders-by-using-character-strings"></a><span data-ttu-id="f1d1c-103">使用字符串命名文件夹</span><span class="sxs-lookup"><span data-stu-id="f1d1c-103">Naming Folders by Using Character Strings</span></span>

  
  
<span data-ttu-id="f1d1c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f1d1c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f1d1c-105">如果在会话过程中经常访问一个或多个文件夹, 请考虑使用[IMsgStore:: SetReceiveFolder](imsgstore-setreceivefolder.md)方法为文件夹分配名称。</span><span class="sxs-lookup"><span data-stu-id="f1d1c-105">If you access one or more folders frequently during a session, consider assigning names to the folders with the [IMsgStore::SetReceiveFolder](imsgstore-setreceivefolder.md) method.</span></span> <span data-ttu-id="f1d1c-106">尽管**IMsgStore:: SetReceiveFolder**主要用于建立特殊文件夹以接收特定邮件类别的传入邮件, 但也可用于将任何文件夹与名称相关联。</span><span class="sxs-lookup"><span data-stu-id="f1d1c-106">Although **IMsgStore::SetReceiveFolder** is used primarily to establish special folders to receive incoming messages for particular message classes, it can also be used to associate any folder with a name.</span></span> <span data-ttu-id="f1d1c-107">该名称可以与消息类相同, 也可以是为客户端使用而自定义的任何字符串。</span><span class="sxs-lookup"><span data-stu-id="f1d1c-107">The name can be the same as the message class or it can be any character string, customized for your client's use.</span></span> <span data-ttu-id="f1d1c-108">将名称与文件夹相关联可减少查找和打开文件夹所需的时间。</span><span class="sxs-lookup"><span data-stu-id="f1d1c-108">Associating a name with a folder decreases the time it takes to find and open the folder.</span></span> 
  

