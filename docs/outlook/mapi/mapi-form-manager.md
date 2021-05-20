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
  
表单管理器是一个实现 [IMAPIFormMgr 接口](imapiformmgriunknown.md) 的对象。 大多数组织将使用 MAPI 提供的表单管理器，称为默认表单管理器。 但是，如果需要，组织可以将默认表单管理器替换为自定义表单管理器。 表单管理器负责在表单库中定位表单、加载表单以响应用户请求，以及将表单安装到用户的本地表单库、文件夹表单库或个人表单库中。 
  
若要使用户与邮件进行交互，必须创建并激活邮件的邮件类的窗体服务器实例，以显示邮件，并针对邮件执行请求的操作。 如主题 [MAPI Form Libraries](mapi-form-libraries.md)中所述，表单的实现可以存在于多个不同位置 (表单库) 并且不能保证表单或它的服务器在本地可用，或者当用户希望与表单库交互时，该表单的服务器将位于运行状态。 表单管理器负责有关定位和激活表单的详细信息。
  
客户端使用表单管理器提供的服务来查找和激活表单。 **IMAPIFormMgr** 接口由表单管理器实现，由客户端调用以访问其服务。 表单管理器是一个基本组件，因为它几乎隐藏了从邮件客户端查找和激活表单的所有详细信息。 
  
加载表单服务器时，默认表单管理器会从找到表单的邮件类实现的第一个表单库中加载表单。 默认表单管理器按以下顺序搜索表单库：
  
1. 用户的本地表单库。 首先搜索此表单库，因为它提供对表单实现（如果实现安装在本地表单库中）的最快访问权限。
    
2. 邮件容器的文件夹表单库 — 存储正在加载的邮件的文件夹。
    
3. 用户的个人表单库。
    
自定义表单管理器可以按任意顺序搜索可用的表单库，也可以实现其他表单库，如组织范围的表单库。 有关表单库的更多详细信息，请参阅[MAPI Form Libraries。](mapi-form-libraries.md) 
  
## <a name="see-also"></a>另请参阅



[MAPI 表单](mapi-forms.md)

