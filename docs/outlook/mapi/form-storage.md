---
title: 窗体存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6ddf9158-3c10-408a-aeaf-5a382c4339e7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c98427ab326ada0b717282dc4077d526780aa45c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568159"
---
# <a name="form-storage"></a>窗体存储

**适用于**： Outlook 2013 |Outlook 2016 
  
尽管不需要知道的如何从物理上隔离存储窗体的所有详细信息，它可了解几个主要概念。 因此之前描述的三种类型的默认窗体管理器支持的表单库，本主题概述了如何存储窗体。
  
表单定义可以从物理上隔离存储在一个或多个 MAPI 消息存储中的文件夹中。 每个 MAPI 文件夹可以被认为是具有用于存储消息对象的两个方面： 标准部件和关联的部件。 文件夹的标准部分包括消息和用户操作的文件夹。
  
相关联的部分包括隐藏的邮件对象与该文件夹，包括表单定义、 视图、 规则模板关联的答复模板，等等。 此备用部件调用文件夹关联的内容表中，并的关联的内容表中的消息集被称为的文件夹关联的信息。 隐藏的邮件的文件夹的必要组成部分，并复制文件夹时标准文件夹内容以及复制。 物理存储为邮件，尽管文件夹关联的内容表中的信息行为更像属性比 like 可查看邮件。 支持的关联的内容表的任何文件夹对象是可存储自定义窗体。 [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)方法可以返回标准内容或关联的文件夹，具体取决于该方法的_ulflags_参数的值的内容。 
  
表单库包含的文件夹关联的内容表中存储的表单定义。 窗体定义包含窗体的属性，该窗体支持的操作，并且即使窗体服务器可执行文件，它将被视为一个或多个邮件附件。
  
此外，窗体可以存储在任何文件或要使用的窗体管理器支持的位置。 默认窗体管理器 MAPI 文件夹中存储窗体服务器，但自定义窗体管理器无法实现自己的窗体服务器的存储。
  
可以有多个绑定到其邮件类别的用户界面。 例如，窗体可以有单独的撰写和阅读用户界面。 正在调用窗体考虑护理的调用适当的用户界面的不同用户请求，具体取决于该窗体的动作。 例如，如果窗体服务器具有单独的撰写和阅读用户界面，撰写用户界面可以自动打开当用户创建窗体的邮件类的新邮件并读取用户界面可以自动打开时用户打开窗体的邮件类的现有邮件。
  
通过调用**IMAPIFormInfo**对象的[IMAPIFormInfo::IMAPIProp](imapiforminfoimapiprop.md)方法，表单定义中存储的信息的大多数位于。 **IMAPIFormInfo**接口简化了通过调用所有的 MAPI 文件夹和消息方法检索信息所需表单信息的访问。 可通过调用[IMAPIFormContainer::ResolveMessageClass](imapiformcontainer-resolvemessageclass.md)方法获取**IMAPIFormInfo**对象。 
  
三种类型的表单库[本地表单库](local-form-libraries.md)、[文件夹表单库](folder-form-libraries.md)和[个人窗体库](personal-form-libraries.md)主题所述。
  
## <a name="see-also"></a>另请参阅

- [MAPI 表单](mapi-forms.md)

