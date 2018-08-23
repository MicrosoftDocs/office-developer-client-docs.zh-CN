---
title: MAPI 窗体管理器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c0bbbd06-d47d-45ad-8179-2372d1d023d0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f78c25285c7ac3f8736006e4a45079a7d9a6d867
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592295"
---
# <a name="mapi-form-manager"></a>MAPI 窗体管理器

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
窗体管理器是实现[IMAPIFormMgr](imapiformmgriunknown.md)接口的对象。 大多数组织将使用 MAPI，称为默认窗体管理器与提供的窗体管理器。 但是，组织可以替换默认窗体管理器自定义窗体管理器如果需要。 窗体管理器负责表单库中查找窗体，加载用户请求的响应中的窗体并安装到用户的本地表单库、 文件夹表单库或个人表单库的表单。 
  
与邮件进行交互的用户，必须创建和激活来显示消息，执行对邮件请求的操作的消息的邮件类的窗体服务器实例。 [MAPI 表单库](mapi-form-libraries.md)的主题中所述，窗体的实现可以存在几个不同的位置 （窗体库） 中，不能保证窗体或其服务器将在本地或为正在运行中的状态时用户希望交互使用它。 负责定位和激活窗体的详细信息窗体管理器。
  
客户端使用提供的窗体管理器服务来查找和激活窗体。 **IMAPIFormMgr**接口由窗体管理器和客户端访问其服务调用。 窗体管理器是必备组件，因为它会隐藏查找并激活消息客户端中的窗体的几乎所有的详细信息。 
  
加载表单服务器时, 的默认窗体管理器从第一个窗体库中找到的窗体的邮件类实现加载窗体。 默认窗体管理器按以下顺序搜索表单库：
  
1. 用户的本地表单库。 因为它提供了最快访问表单的实现，如果实现安装在本地表单库，首先搜索此表单库。
    
2. 消息的容器文件夹表单库 — 要加载的消息存储在其中的文件夹。
    
3. 用户的个人窗体库。
    
自定义窗体管理器可以按任意顺序，搜索可用表单库，也可以实现其他表单库，如组织范围内表单库。 表单库的详细信息，请参阅[MAPI 表单库](mapi-form-libraries.md)。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表单](mapi-forms.md)

