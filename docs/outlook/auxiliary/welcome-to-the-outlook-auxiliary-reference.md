---
title: 欢迎使用 Outlook 辅助参考
manager: soliver
ms.date: 09/10/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 2e48a625-b3f7-9fd0-253e-fe12a1aca446
description: Outlook 辅助参考包含概念性内容和四组 Api、 代码示例和可再发行组件安装程序允许开发人员扩展和将与 Outlook 集成的参考文档。 本参考中的 Api 由 Outlook 扩展性，Outlook 对象模型之外公开。
ms.openlocfilehash: 445d35c12e4c8984d47adcef3ecf50ebd881875b
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384554"
---
# <a name="welcome-to-the-outlook-auxiliary-reference"></a>欢迎使用 Outlook 辅助参考

Outlook 辅助参考包含概念性内容和四组 Api、 代码示例和可再发行组件安装程序允许开发人员扩展和将与 Outlook 集成的参考文档。 本参考中的 Api 由 Outlook 扩展性，Outlook 对象模型之外公开。 
  
如果你是第一次开发 Outlook 解决方案，请参阅[选择某个 API 或技术开发适用于 Outlook 的解决方案](../selecting-an-api-or-technology-for-developing-solutions-for-outlook.md)，以确定最适合你需求的 API 和技术。 

有关 Outlook 对象模型的特定信息，请参阅[Outlook VBA 参考 （英文）](https://msdn.microsoft.com/library/75e4ad96-62a2-49d2-bc51-48ceab50634c%28Office.15%29.aspx)。 

有关消息处理 API (MAPI) 支持的 Outlook 的特定信息，请参阅[Outlook MAPI 参考 （英文）](https://msdn.microsoft.com/library/3d980b86-7001-4869-9780-121c6bfc7275%28Office.15%29.aspx)。

## <a name="conceptual"></a>概念 

概念讨论包括下列主题：
  
- [有关反垃圾邮件设置](about-anti-spam-settings.md)
    
- [管理 POP3 帐户的邮件下载](managing-message-downloads-for-pop3-accounts.md)
    
- [查找一个 POP3 帐户的消息下载历史记录](locating-the-message-download-history-for-a-pop3-account.md)
    
- [分析 POP3 帐户的邮件下载历史记录](parsing-the-message-download-history-for-a-pop3-account.md)
    
- [关于自定义项目类型的冲突解决](about-conflict-resolution-for-custom-item-types.md)
    
- [关于脱机通讯簿的上次更新时间](about-the-last-update-time-of-an-offline-address-book.md)
    
- [关于注册新域以进行自动配置](about-registering-a-new-domain-for-automatic-configuration.md)
    
- [About meeting requests as informational updates and full updates](about-meeting-requests-as-informational-updates-and-full-updates.md)
    
- [有关以编程方式的夏时制调整日历](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)（还有可再发行软件包的安装程序的第三方日历调整工具，以早期版本的 Outlook 也适用于 Outlook 2010 相。 若要下载安装程序，请参阅[Outlook 2010： 辅助参考可再发行组件安装程序和头文件定位日历的](https://www.microsoft.com/downloads/details.aspx?FamilyID=77748863-4352-4b99-ae57-1d4ae803983b)。)
    
- [关于将 TZDEFINITION 保存到流以提交到二进制属性](about-persisting-tzdefinition-to-a-stream-to-commit-to-a-binary-property.md)

## <a name="reference"></a>参考

参考内容包括以下组件：
  
- [由 Outlook 导出 Api](about-apis-exported-by-outlook.md)包括函数和最初实现供内部使用并用于公共现已公开的数据结构。 
    
- [帐户管理 API](about-the-account-management-api.md)提供了访问用户帐户信息和帐户更改的通知。 
    
- [数据降级层 API](about-the-data-degradation-layer-api.md)支持访问首选的字符格式，而不是对象的本机字符格式中的 Outlook 项目的客户端。 
    
- [忙/闲 API](about-the-free-busy-api.md)提供了有关特定时间范围内的特定用户帐户的忙/闲状态信息。 

## <a name="sample-tasks"></a>示例任务

Outlook 辅助参考中的示例操作方法任务包括：
    
- [确定某个 Outlook 项目是否已修改但未保存（Outlook 辅助参考）](how-to-determine-if-outlook-item-has-been-modified-but-not-saved.md)
    
- [分析二进制属性读取 TZDEFINITION 结构的流](how-to-parse-stream-from-binary-property-to-read-tzdefinition-structure.md)
    
- [分析二进制属性读取 TZREG 结构的流](how-to-parse-a-stream-from-a-binary-property-to-read-the-tzreg-structure.md)
    
- [从约会中读取时区属性](how-to-read-time-zone-properties-from-an-appointment.md)
    
- [指定是否要在 Outlook（Outlook 辅助参考）中显示联系人的图片](https://msdn.microsoft.com/library/office/gg262879.aspx)
    
- [使用访问忙/闲数据的相对时间](how-to-use-relative-time-to-access-free-busy-data.md)
    
常量、 类型定义和开发人员使用的其他功能而必须实现的接口，列出了每个 API 的引用。
  
> [!NOTE]
> 开发人员必须实现这些 Api，只会在此引用中记录。 某些接口成员和方法参数被命名为占位符因为它们仅供内部使用的 Outlook，如有更改，恕不另行通知。 
  

