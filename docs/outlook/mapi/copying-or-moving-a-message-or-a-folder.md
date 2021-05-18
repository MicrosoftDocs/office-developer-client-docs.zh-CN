---
title: 复制或移动邮件或文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 72290fd3-00d7-4055-bbfa-0c47b6e0f62d
description: 上次修改时间：2011 年 11 月 8 日
ms.openlocfilehash: c5e92c44d7078560ed84d72b3477d5cf2e809353
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413498"
---
# <a name="copying-or-moving-a-message-or-a-folder"></a>复制或移动邮件或文件夹
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端可以使用以下四种方法之一复制或移动邮件或文件夹：
  
- [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md)
    
- [IMAPIFolder::CopyMessages](imapifolder-copymessages.md)
    
- [IMAPIProp::CopyTo](imapiprop-copyto.md)
    
- [IMAPIProp::CopyProps](imapiprop-copyprops.md)
    
通过设置适当的标志和参数 **，CopyTo** 和 **CopyProps** 可以像 **CopyFolder** 或 **CopyMessages** 一样工作。 在决定调用哪种方法时，请考虑以下问题：
  
- 复制或移动文件夹还是邮件？
    
- 您有多少关于要移动或复制的文件夹或邮件的信息？
    
- 将移动或复制多少文件夹或邮件属性？
    
可以使用 **IMAPIProp** 方法复制或移动文件夹或邮件。 **IMAPIFolder：：CopyMessages** 仅适用于消息; **IMAPIFolder：：CopyFolder** 仅适用于文件夹。 
  
虽然使用 **IMAPIFolder** 方法不需要任何有关要复制或移动的文件夹或邮件支持的属性的知识，但您必须了解一些使用 **IMAPIProp** 方法的知识。 使用 **IMAPIProp：：CopyProps，** 必须能够明确指定要复制或移动的文件夹或邮件属性。 使用 **IMAPIProp：：CopyTo**，除非要复制或移动所有属性，否则必须明确指定应排除哪些属性。 有关这些方法详细信息，请参阅复制 [MAPI 属性](copying-mapi-properties.md)。
  
要复制或移动的属性数可能会影响有关使用哪种方法的决定。 如果要复制或移动多个消息，请调用 **IMAPIFolder：：CopyMessages**。 另一种选择是调用 **IMAPIProp：：CopyProps** 以仅复制文件夹的 **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 属性。 以下过程演示如何使用 **CopyMessages**。 
  
### <a name="to-copy-or-move-one-or-more-messages"></a>复制或移动一个或多个邮件
  
1. 查找源和目标文件夹的有效条目标识符。
    
2. 通过调用 [IMAPISession：：OpenEntry](imapisession-openentry.md) 或 [IMsgStore：：OpenEntry](imsgstore-openentry.md) 并设置 MAPI_MODIFY 标志，以读/写模式打开这些文件夹。 
    
3. 检查从 **OpenEntry** 返回的接口指针是 **IMAPIFolder** 接口指针。 如果没有，请强制转换到 LPMAPIFOLDER 类型。 
    
4. 创建一个条目标识符数组，该数组代表要复制或移动的一个或多个邮件。 
    
5. 调用 **设置了以下标志的 IMAPIFolder：：CopyMessages：** 
    
   - MESSAGE_MOVE，如果要执行移动操作。 
    
   - MESSAGE_DIALOG  _ulUIParam_ 参数中指定并传递窗口句柄（如果希望文件夹显示进度指示器）。 
    
6. 释放源文件夹和目标文件夹的 **IMAPIFolder** 指针。 
    
如果要将文件夹的完整内容复制到另一个文件夹，请调用源文件夹的 **IMAPIFolder：：CopyFolder** 或 **IMAPIProp：：CopyTo** 方法。 
  
若要复制文件夹的一些属性，请调用 **其 IMAPIProp：：CopyProps** 方法。 若要复制大多数文件夹的属性，请调用 **IMAPIProp：：CopyTo**。 
  
例如，如果要复制文件夹的 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和 **PR_COMMENT** ([PidTagComment](pidtagcomment-canonical-property.md)) 属性，则有以下选项：
  
- 调用 **IMAPIFolder：：CopyFolder** 复制所有文件夹属性，然后从新文件夹中删除不需要的属性。 
    
- 调用 **CopyTo** 并排除文件夹的所有属性，PR_DISPLAY_NAME **和****PR_COMMENT**。 
    
- 调用 **CopyProps**，在 **include** PR_DISPLAY_NAME **PR_COMMENT** 和 PR_COMMENT。 
    
在这种情况下 **，CopyProps** 是最佳选择，因为它用于复制一小组属性，也是要实现的最简单调用。 
  
若要仅复制或移动文件夹属性（不包括消息），请调用文件夹的 **IMAPIProp：：CopyTo** 方法，并排除以下属性： 
  
- **PR_CONTAINER_CONTENTS (** [PidTagContainerContents)](pidtagcontainercontents-canonical-property.md)
    
- **PR_FOLDER_ASSOCIATED_CONTENTS (** [PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 
    
复制方法可以返回S_OK，指示总成功、MAPI_W_PARTIAL_COMPLETION、指示部分成功或错误。 如果MAPI_W_PARTIAL_COMPLETION，请使用 HR_FAILED **宏访问** 更具体的错误。 有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。
  
如果将邮件从一个邮件存储复制到另一个邮件存储，但 Unicode 不受两者支持，请注意，由于代码页转换，信息可能会丢失。 通常，您不知道邮件存储是否支持一种或两种格式，因此无法确定是复制文本属性为 ASCII 字符串还是 Unicode 字符串。 如果支持 Unicode，请尝试执行 Unicode 副本;如果失败，错误值MAPI_E_BAD_CHARWIDTH ASCII。
  

