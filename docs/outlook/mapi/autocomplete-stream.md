---
title: 自动完成流
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: d4f380fa-2ed9-4c7c-9ef3-b32f8409f657
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: aadfba3e2674c35019a2e5f3eb374fbed1ad2a75
ms.sourcegitcommit: 0419850d5c1b3439d9da59070201fb4952ca5d07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/28/2020
ms.locfileid: "49734222"
---
# <a name="autocomplete-stream"></a>自动完成流

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
除了知道 Microsoft Outlook 如何与自动完成流交互之外，还必须了解自动完成流的二进制格式。
  
自动完成流是一组收件人属性行，它们与仅由 Microsoft Outlook 2013、Microsoft Outlook 2010、Microsoft Office Outlook 2007 和 Microsoft Outlook 2003 使用的一些记帐元数据一起保存为二进制流。 元数据与 Outlook 与自动完成流的交互相关，因此第三方在保存修改后的自动完成流时必须保留每个元数据块中的内容。 换句话说，第三方应仅修改二进制格式的行集部分，并保留自动完成流的元数据块中已有的内容。
  
## <a name="stream-visualization"></a>流可视化

自动完成流的高级别布局如下所示：
  
元数据 (4 字节) 
  
主版本号 (4 字节) 
  
次要版本号 (4 字节) 
  
n 个行 (4 个字节) 
  
第一行中属性 p (4 字节) 
  
属性 1 的属性标记大小 (4 字节) 
  
属性 1 的保留数据 (4 字节) 
  
属性 1 的值联合 (8 字节) 
  
属性 1 的值数据 (0 或可变字节) 
  
…  (P-1 属性 2 到属性 1) 
  
属性 p 的属性标记大小为 4 (字节) 
  
属性 p 的保留数据 (4 字节) 
  
属性 p 的值联合 (8 字节) 
  
属性 p 的值数据 (0 或可变字节) 
  
第二行的属性 q 数 (4 字节) 
  
…  (第二行的属性) 
  
…  (第 3 行到第 n-1 行) 
  
第 n 行中属性 r (4 字节) 
  
…  (行 n 的属性) 
  
额外信息字节计数 EI (4 字节) 
  
有关 EI (字节数的) 
  
元数据 (8 字节) 
  
有关二进制结构的示例，请参阅 Outlook [2003/2007 NK2](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)文件格式和开发人员指南中的二进制示例。
  
## <a name="high-level-layout"></a>高级布局

一般来说，自动完成流的布局如下所示：
  
|**数值数据**|**字节数**|
|:-----|:-----|
|Metadata  <br/> |4   <br/> |
|主版本号  <br/> |4   <br/> |
|次要版本号  <br/> |4   <br/> |
|行集  <br/> |变量  <br/> |
|额外信息字节计数 EI  <br/> |4   <br/> |
|额外信息  <br/> |EI  <br/> |
|Metadata  <br/> |8   <br/> |
   
读取此流时，如果主要版本不同于 12，则不应读取或写入此流。 自动完成流的当前次要版本为 0，其中额外信息字节计数设置为 0。 如果次要版本不为 0，则读取流时需要读取和写入流时保留的额外信息。 编写流时，还需要保留次要版本。 如果未保留这两者，则Outlook额外信息的实例将丢失数据。 
  
> [!NOTE]
> 应用程序不得向"额外信息"字段添加自定义数据或更改次要版本，因为此功能是支持格式的 Outlook 扩展，而不是任意第三方扩展。 
  
## <a name="row-set-layout"></a>行集布局

行集布局如下所示： 
  
|**数值数据**|**字节数**|
|:-----|:-----|
|行数  <br/> |4   <br/> |
|Rows  <br/> |变量  <br/> |
   
行数标识二进制流序列的下一部分中的行数。
  
## <a name="row-layout"></a>行布局

每行的格式如下：
  
|**数值数据**|**字节数**|
|:-----|:-----|
|属性数  <br/> |4   <br/> |
|属性  <br/> |变量  <br/> |
   
属性数标识二进制流序列的下一部分中的属性数。
  
## <a name="property-layout"></a>属性布局

每个属性的格式如下：
  
|**数值数据**|**字节数**|
|:-----|:-----|
|属性标记  <br/> |4   <br/> |
|保留数据  <br/> |4   <br/> |
|属性值联合  <br/> ||
|数值数据  <br/> |0 或变量 (属性标记值)   <br/> |
   
## <a name="interpreting-the-property-value"></a>解释属性值

属性值联合值和值数据将基于属性块前 4 个字节中的属性标记进行解释。 此属性标记的格式与 MAPI 属性标记的格式相同。 属性标记的位 0 到 15 是属性的类型。 位 16 到 31 是属性的标识符。 属性类型确定属性的其余部分的读取方法。
  
## <a name="static-value"></a>静态值

某些属性没有值数据，并且只有联合数据。 以下属性类型 (来自 Property Tag) 应按如下方式解释 8 字节 Property Union 数据：
  
|**Prop 类型**|**Property Union Interpretation**|
|:-----|:-----|
|PT_I2  <br/> |short int  <br/> |
|PT_LONG  <br/> |long  <br/> |
|PT_ERROR  <br/> |long  <br/> |
|PT_R4  <br/> |float  <br/> |
|PT_DOUBLE  <br/> |double  <br/> |
|PT_BOOLEAN  <br/> |short int  <br/> |
|PT_SYSTIME  <br/> |FILETIME  <br/> |
|PT_I8  <br/> |LARGE_INTEGER  <br/> |
   
## <a name="dynamic-values"></a>动态值

其他属性在包含 Property Tag、保留数据和属性值联合的前 16 个字节之后的值数据块中具有数据。 与静态值不同，存储在 8 字节属性值联合中的数据与读取无关。 编写时，请确保用某些内容填充这 8 个字节。 但是，8 字节的内容不是很重要。 在动态值中，属性标记的类型确定如何解释值数据。
  
PT_STRING8 
  
|**数值数据**|**字节数**|
|:-----|:-----|
|字节数 n  <br/> |4   <br/> |
|要解释为 ANSI 字符串字符串的字节 (NULL 终止符)   <br/> |n  <br/> |
   
PT_CLSID
  
|**数值数据**|**字节数**|
|:-----|:-----|
|要解释为 GUID 的字节数  <br/> |16   <br/> |
|||
   
PT_BINARY 
  
|**数值数据**|**字节数**|
|:-----|:-----|
|字节数 n  <br/> |4   <br/> |
|要解释为字节数组的字节数  <br/> |n  <br/> |
   
PT_MV_BINARY
  
|**数值数据**|**字节数**|
|:-----|:-----|
|二进制数组 X 的数量  <br/> |4   <br/> |
|包含 X 二进制数组的字节数。 每个数组的解析方式应完全如PT_BINARY字节运行一样。  <br/> |变量  <br/> |
   
PT_MV_STRING8 (Outlook 2013 Outlook 2010 Outlook 2013) 
  
|**数值数据**|**字节数**|
|:-----|:-----|
|ANSI 字符串 X 的数量  <br/> |4   <br/> |
|包含 X ANSI 字符串的字节数。 每个字符串应完全按照字节PT_STRING8解释。  <br/> |变量  <br/> |
   
PT_MV_UNICODE (Outlook 2013 Outlook 2010 Outlook 2013) 
  
|**数值数据**|**字节数**|
|:-----|:-----|
|UNICODE 字符串 X 的数量  <br/> |4   <br/> |
|包含 X UNICODE 字符串的字节数。 每个字符串应完全按照字节PT_UNICODE解释。  <br/> |变量  <br/> |
   
## <a name="significant-properties"></a>重要属性

如本主题前面所述，表示属性的二进制块具有对应于通讯簿收件人的属性的属性标记。 对于此处未列出的属性，可在 上查找属性说明 https://msdn.microsoft.com/library/cc433490(EXCHG.80).aspx 。
  
|**属性名称**|**属性标记**|**说明 (有关详细信息，请参阅 MSDN)**|
|:-----|:-----|:-----|
|PR_NICK_NAME_W (传输的流，特定于仅自动完成流)   <br/> |0x6001001f  <br/> |此属性必须首先在每个收件人行中。 它在功能上充当收件人行的键标识符。  <br/> |
|PR_ENTRYID  <br/> |0x0FFF0102  <br/> |收件人的通讯簿条目标识符。  <br/> |
|PR_DISPLAY_NAME_W  <br/> |0x3001001F  <br/> |收件人的显示名称。  <br/> |
|PR_EMAIL_ADDRESS_W  <br/> |0x3003001F  <br/> |收件人的电子邮件地址，例如 johndoe@contoso.com (或 /o=Contoso/OU=Foo/cn=Recipients/cn=johndoe)   <br/> |
|PR_ADDRTYPE_W  <br/> |0x3002001F  <br/> |收件人的地址类型 (例如 SMTP 或 EX) 。  <br/> |
|PR_SEARCH_KEY  <br/> |0x300B0102  <br/> |收件人的 MAPI 搜索密钥。  <br/> |
|PR_SMTP_ADDRESS_W  <br/> |0x39FE001f  <br/> |收件人的 SMTP 地址。  <br/> |
|PR_DROPDOWN_DISPLAY_NAME_W (传输的流，特定于仅自动完成流)   <br/> |0X6003001f  <br/> |自动完成列表中显示的显示字符串。  <br/> |
|PR_NICK_NAME_WEIGHT (传输的流，特定于仅自动完成流)   <br/> |0x60040003  <br/> |此自动完成条目的权重。 权重用于确定在匹配自动完成列表时自动完成条目发生的顺序。 权重较高的条目显示在权重较低的条目之前。 完整的自动完成列表按此属性排序。 权重会随着时间的推移而定期减小，并且当用户向此收件人发送电子邮件时，权重也会增加。 有关此属性的详细信息，请参阅本主题稍后的说明。  <br/> |
   
PR_NICK_NAME_WEIGHT
  
自动完成流中的行集按 PR_NICK_NAME_WEIGHT 属性按降序排序，并且自动完成流应始终保留此排序特征。 因此，对行权重的任何更改还应确保行的位置保持整组行的排序顺序。 行集的任何添加内容都应插入到正确的位置以保持排序顺序。
  
此权重的最小值为 0x1，最大值为 LONG_MAX。 权重的其他任何值都被视为无效。
  
当 Outlook 2007 向收件人发送邮件或解析收件人时，该收件人的权重将增加0x2000。
  

