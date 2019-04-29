---
title: MAPI 表单管理器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c0bbbd06-d47d-45ad-8179-2372d1d023d0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3059183103ca2552505486b5ec54366729ae4ec3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430194"
---
# <a name="mapi-form-manager"></a>MAPI 表单管理器

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表单管理器是一个实现[IMAPIFormMgr](imapiformmgriunknown.md)接口的对象。 大多数组织将使用 MAPI 提供的窗体管理器, 称为 "默认表单管理器"。 但是, 如果需要, 组织可以将默认表单管理器替换为自定义表单管理器。 表单管理器负责查找表单库中的表单、加载表单以响应用户请求, 以及将表单安装到用户的本地表单库、文件夹表单库或个人表单库中。 
  
若要使用户与邮件进行交互, 必须创建并激活邮件邮件类的窗体服务器实例以显示该邮件, 并对邮件执行请求的操作。 如[MAPI 表单库](mapi-form-libraries.md)主题中所述, 表单的实现可以存在于多个不同的位置 (表单库) 中, 并且不能保证当用户要进行交互时, 窗体或其服务器将在本地可用或处于运行状态。使用它。 表单管理器负责查找和激活表单的详细信息。
  
客户端使用由表单管理器提供的服务来查找和激活表单。 **IMAPIFormMgr**接口由表单管理器实现, 并由客户端调用以访问其服务。 表单管理器是一个重要的组件, 因为它隐藏了从邮件客户端查找和激活表单的几乎所有详细信息。 
  
加载表单服务器时, 默认表单管理器会从第一个表单库加载表单, 在该表单库中找到表单的邮件类的实现。 默认表单管理器将按以下顺序搜索表单库:
  
1. 用户的本地表单库。 将首先搜索此表单库, 因为如果在本地表单库中安装了该实现, 则它可以最快地访问表单实现。
    
2. 邮件容器的文件夹表单库—存储正在加载的邮件所在的文件夹。
    
3. 用户的个人表单库。
    
自定义表单管理器可以按任何顺序搜索可用的表单库, 也可以实现其他表单库, 如组织范围的表单库。 有关表单库的更多详细信息, 请参阅[MAPI 表单库](mapi-form-libraries.md)。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表单](mapi-forms.md)

