---
title: 复制或移动邮件或文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 72290fd3-00d7-4055-bbfa-0c47b6e0f62d
description: 上次修改时间： 2011 年 11 月 8 日
ms.openlocfilehash: 97e7c90c2fdc715d7d0749300cc62854fffa6447
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563980"
---
# <a name="copying-or-moving-a-message-or-a-folder"></a>复制或移动邮件或文件夹
  
**适用于**： Outlook 2013 |Outlook 2016 
  
客户端可以使用四种方法之一来复制或移动邮件或文件夹：
  
- [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md)
    
- [IMAPIFolder::CopyMessages](imapifolder-copymessages.md)
    
- [IMAPIProp::CopyTo](imapiprop-copyto.md)
    
- [IMAPIProp::CopyProps](imapiprop-copyprops.md)
    
通过设置的相应标志和参数，可以进行**CopyTo**和**CopyProps**一样**CopyFolder**或**CopyMessages**工作。 在决定哪种方法来调用时，请考虑以下问题：
  
- 您所复制或移动的文件夹或一条消息？
    
- 多少有关邮件移动或复制的文件夹知道？
    
- 文件夹的数量或将移动或复制邮件的属性？
    
**IMAPIProp**方法可用于复制或移动的文件夹或一条消息。 **IMAPIFolder::CopyMessages**处理邮件仅;与文件夹仅适用于**IMAPIFolder::CopyFolder** 。 
  
而使用**IMAPIFolder**方法不需要任何知识支持的邮件复制或移动的文件夹的属性，您必须具有一些知识使用**IMAPIProp**方法。 **IMAPIProp::CopyProps**，您必须能够显式指定其要复制或移动的文件夹或邮件属性。 与**IMAPIProp::CopyTo**，除非您想要复制或移动的所有属性，必须明确指定应排除哪些功能。 有关这些方法的详细信息，请参阅[复制 MAPI 属性](copying-mapi-properties.md)。
  
要复制或移动的属性数会影响您决定使用哪种方法。 如果您正在复制或移动多个邮件，呼叫**IMAPIFolder::CopyMessages**。 备用选择是将调用**IMAPIProp::CopyProps**复制仅文件夹的**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 属性。 下面的过程演示如何使用**CopyMessages**。 
  
### <a name="to-copy-or-move-one-or-more-messages"></a>复制或移动一个或多个邮件
  
1. 找到的源和目标文件夹的有效项标识符。
    
2. 通过调用[IMAPISession::OpenEntry](imapisession-openentry.md)或[IMsgStore::OpenEntry](imsgstore-openentry.md)并设置 MAPI_MODIFY 标志以读/写模式打开这些文件夹。 
    
3. 检查**OpenEntry**从返回的接口指针是**IMAPIFolder**接口的指针。 否则，将其转换为 LPMAPIFOLDER 类型。 
    
4. 创建表示一个或多个邮件复制或移动的项标识符的数组。 
    
5. 设置了以下 flags 呼叫**IMAPIFolder::CopyMessages** : 
    
   - MESSAGE_MOVE，如果您想要执行移动操作。 
    
   - MESSAGE_DIALOG 并传递一个窗口中的处理_ulUIParam_参数，如果您想要显示进度指示器的文件夹。 
    
6. 发行版的源和目标文件夹的**IMAPIFolder**指针。 
    
如果您想要将某个文件夹的完整内容复制到另一个文件夹，调用源文件夹的**IMAPIFolder::CopyFolder**或**IMAPIProp::CopyTo**方法。 
  
若要将复制几个文件夹的属性，请调用其**IMAPIProp::CopyProps**方法。 若要将复制的大多数某个文件夹的属性，请调用**IMAPIProp::CopyTo**。 
  
例如，如果您想要复制的文件夹**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和**PR_COMMENT** ([PidTagComment](pidtagcomment-canonical-property.md)) 属性，您具有以下选项：
  
- 调用**IMAPIFolder::CopyFolder**复制的所有文件夹属性，然后删除不需要的新文件夹中。 
    
- 调用**CopyTo**和排除所有除**PR_DISPLAY_NAME**和**PR_COMMENT**文件夹的属性。 
    
- 调用**CopyProps**， **PR_DISPLAY_NAME**和**PR_COMMENT**传递包含数组中。 
    
在这种情况下， **CopyProps**是最佳选择，因为它为了可用于将复制一小组属性和是最简单的呼叫，以实现。 
  
若要复制或移动仅文件夹属性中，不包括消息的情况下，调用该文件夹的**IMAPIProp::CopyTo**方法并不包括以下属性： 
  
- **PR_CONTAINER_CONTENTS**([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))
    
- **PR_FOLDER_ASSOCIATED_CONTENTS**([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))
    
复制方法可以返回 S_OK，指示总成功，MAPI_W_PARTIAL_COMPLETION，指示部分成功或错误。 如果返回 MAPI_W_PARTIAL_COMPLETION，使用**HR_FAILED**宏访问更具体的错误。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
  
如果将消息从一个消息存储库复制到另一个和 Unicode 不支持这二者，则应注意的信息可能丢失由于代码页转换。 通常您无法知道是否消息存储库支持一种或两个格式，使其无法确定是否将复制文本属性作为字符串 ASCII 或 Unicode 字符串。 如果您支持 Unicode，尝试执行 Unicode 复制;如果失败的错误值 MAPI_E_BAD_CHARWIDTH，，借助 ASCII。
  

