---
title: PidTagStoreSupportMask 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStoreSupportMask
api_type:
- COM
ms.assetid: ada5694a-b5b1-471f-be33-906fc052681a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1936cb8e95e3faef8c92d6bf28f5b63b3ff72df5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572702"
---
# <a name="pidtagstoresupportmask-canonical-property"></a>PidTagStoreSupportMask 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含的标志位掩码的客户端应用程序查询，以确定的消息存储的特征。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_STORE_SUPPORT_MASK  <br/> |
|标识符：  <br/> |0x340D  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |其他  <br/> |
   
## <a name="remarks"></a>注解

此属性会泄露打算将其发送一条消息的客户端应用程序的消息存储的功能。 标志可支持的客户端或另一个存储，如是否发送**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 或仅**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 的决策。 客户端应始终不将**PR_STORE_SUPPORT_MASK**;试图设置此标志返回 MAPI_E_COMPUTED。 
  
可以为**PR_STORE_SUPPORT_MASK**位掩码设置一个或多个以下标志： 
  
STORE_ANSI_OK
  
> （131072、 0x00020000）消息存储库支持属性包含 ANSI （8 位） 字符。
    
STORE_ATTACH_OK 
  
> （32、 0x00000020）消息存储库支持邮件附件 （OLE 或非 OLE）。 
    
STORE_CATEGORIZE_OK 
  
> (1024，0x00000400)消息存储支持表的分类的的视图。 
    
STORE_CREATE_OK 
  
> （16、 0x00000010）消息存储库支持创建新邮件。 
    
STORE_ENTRYID_UNIQUE 
  
> （1，0x00000001）消息存储库中的对象的项标识符是唯一的即永远不会存储的生命周期内重用。 
    
STORE_HTML_OK 
  
> （65536、 0x00010000）消息存储库支持 HTML 邮件，存储在**PR_BODY_HTML** ([PidTagBodyHtml](pidtagbodyhtml-canonical-property.md)) 属性。 如果您的开发环境使用 MAPIDEFS。H 文件，不包括 STORE_HTML_OK，则改用 0x00010000 的值。 
    
STORE_ITEMPROC
  
> （2097152、 0x00200000）换行的 PST 存储区中指示当一个新的邮件到达存储，存储执行规则和单独的处理邮件的垃圾邮件筛选器。 存储呼叫[IMAPISupport::Notify](imapisupport-notify.md)，设置**fnevNewMail**作为一个参数传递，然后将新消息的详细信息传递到侦听客户端的[通知](notification.md)结构中。 随后，侦听客户端接收通知时，它不处理邮件的规则。 
    
STORE_LOCALSTORE
  
> （524288、 0x00080000）此标志保留，不应使用。
    
STORE_MODIFY_OK 
  
> （8，0x00000008）消息存储库支持其现有的邮件的修改。 
    
STORE_MV_PROPS_OK 
  
> （512、 0x00000200）消息存储库支持多值的属性，按原样的整个保存一个多值属性的值顺序稳定性操作，并且支持实例化的表中的多值属性。 
    
STORE_NOTIFY_OK 
  
> （256、 0x00000100）消息存储库支持通知。 
    
STORE_OLE_OK 
  
> （64、 0x00000040）消息存储库支持 OLE 附件。 OLE 数据可通过**IStorage**界面，例如，可通过**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 属性。 
    
STORE_PUBLIC_FOLDERS 
  
> （16384、 0x00004000）此存储区中的文件夹是公共 （多用户），不专用 (可能是多实例，但不是多的用户)。 
    
STORE_PUSHER_OK
  
> （8388608、 0x00800000）MAPI 协议处理程序将不存储进行爬网，并存储负责向索引器已编制索引的邮件推送通知通过任何更改。
    
STORE_READONLY 
  
> （2，0x00000002:uc）消息存储的所有接口都具有只读访问权限级别。 
    
STORE_RESTRICTION_OK 
  
> (4096，0x00001000)消息存储支持的限制。 
    
STORE_RTF_OK 
  
> (2048年 0x00000800)消息存储库支持富文本格式 (RTF) 消息，通常压缩，并存储本身保持**PR_BODY**和**PR_RTF_COMPRESSED**同步。 
    
STORE_RULES_OK
  
> （268435456、 0x10000000）指示的规则应存储在此 PST 存储区中，即使它不是默认存储。 与**NON_EMS_XP_SAVE**结合使用时**STORE_RULES_OK** ，都能够在非默认 PST 自动换行存储上运行规则。
    
STORE_SEARCH_OK 
  
> （4，0x00000004）消息存储库支持搜索结果文件夹。 
    
STORE_SORT_OK 
  
> (8192，0x00002000)消息存储支持表的排序的视图。 
    
STORE_SUBMIT_OK 
  
> （128、 0x00000080）消息存储库支持标记提交的邮件。 
    
STORE_UNCOMPRESSED_RTF 
  
> （32768、 0x00008000）消息存储在未压缩的窗体中支持 RTF 邮件存储。 由值**dwMagicUncompressedRTF**流标头中标识未压缩的 RTF 流。 RTFLIB 中定义的**dwMagicUncompressedRTF**值。H 文件。 
    
STORE_UNICODE_OK
  
> （262144、 0x00040000）指示消息存储库支持 Unicode 存储。 客户端可以查看此标志以确定是请求还是将 Unicode 信息保存到存储的状态。 
    
总是可以存储一条消息的 RTF 版本，即使不识别 RTF 的消息存储库。 如果特定存储未设置 STORE_RTF_OK 位，维护 RTF 版本的客户端必须本身调用[RTFSync](rtfsync.md)函数保留为文本内容同步的**PR_BODY**和**PR_RTF_COMPRESSED**版本。 RTF 始终存储在**PR_RTF_COMPRESSED**，是否或不实际压缩。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXMSG]](http://msdn.microsoft.com/library/b046868c-9fbf-41ae-9ffb-8de2bd4eec82%28Office.15%29.aspx)
  
> 介绍用于发送到客户端上共享文件夹相关的信息的消息的格式。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

