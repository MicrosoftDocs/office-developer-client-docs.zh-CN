---
title: 自动完成流
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: d4f380fa-2ed9-4c7c-9ef3-b32f8409f657
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7fc1fae4ed648d59c273b20ced247f6d20e01a6f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774600"
---
# <a name="autocomplete-stream"></a>自动完成流

  
  
**适用于**： Outlook 
  
除了知道 Microsoft Outlook 如何与自动完成流交互之外，还必须了解自动完成流的二进制格式。
  
自动完成流是一组收件人属性行，它们与仅由 Microsoft Outlook 2013、Microsoft Outlook 2010、Microsoft Office Outlook 2007 和 Microsoft Outlook 2003 使用的一些记帐元数据一起保存为二进制流。 元数据与 Outlook 与自动完成流的交互相关，因此第三方在保存修改后的自动完成流时必须保留每个元数据块中的内容。 换句话说，第三方应仅修改二进制格式的行集部分，并保留自动完成流的元数据块中已有的内容。
  
## <a name="stream-visualization"></a>数据流可视化

自动完成流的高级别布局如下所示：
  
元数据（4 个字节）
  
主要版本号（4 个字节）
  
次要版本号（4 个字节）
  
行 n 的数量（4 个字节）
  
行 1 中属性 p 的数量（4 个字节）
  
属性 1 的属性标记（4 个字节）
  
属性 1 的保留数据（4 个字节）
  
属性 1 的值联合（8 个字节）
  
属性 1 的值数据（0 个或变量字节）
  
… （属性 2 至属性 P-1）
  
属性 p 的属性标记（4 个字节）
  
属性 p 的保留数据（4 个字节）
  
属性 p 的值联合（8 个字节）
  
属性 p 的值数据（0 个或可变字节）
  
行 2 中属性 q 的数量（4 个字节）
  
… （行 2 的属性）
  
… （行 3 至行 n-1）
  
行 n 中属性 r 的数量（4 个字节）
  
… （行 n 的属性）
  
额外信息字节计数 EI（4 个字节）
  
额外信息（EI 个字节）
  
元数据（8 个字节）
  
有关二进制结构的示例，请参阅 [Outlook 2003/2007 NK2 文件格式和开发人员指南](http://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)。
  
## <a name="high-level-layout"></a>高级别布局

从广义上讲，自动完成流的布局如下所示：
  
|**数值数据**|**字节数**|
|:-----|:-----|
|元数据  <br/> |4  <br/> |
|主要版本号  <br/> |4  <br/> |
|次要版本号  <br/> |4  <br/> |
|行集  <br/> |变量  <br/> |
|额外信息字节计数 EI  <br/> |4  <br/> |
|额外信息  <br/> |EI  <br/> |
|元数据  <br/> |8  <br/> |
   
读取此数据流时，如果主要版本不同于 12，则不应读取或写入此数据流。 自动完成流的当前次要版本为 0，其额外信息字节计数设置为 0。 如果次要版本不同于 0，则在读取数据流时需要读取的额外信息中将存在信息，并在写入数据流时保留。 写入数据流时还需要保留次要版本。 如果未保留这两者，则写入额外信息的 Outlook 实例将会丢失数据。 
  
> [!NOTE]
> 应用程序不得将自定义数据添加到“额外信息”字段或更改次要版本，因为此功能是为了支持对格式的 Outlook 扩展而不是任意第三方扩展。 
  
## <a name="row-set-layout"></a>行集布局

行集布局如下所示： 
  
|**数值数据**|**字节数**|
|:-----|:-----|
|行数  <br/> |4  <br/> |
|行  <br/> |变量  <br/> |
   
行数将标识二进制流序列的下一部分中有多少行。
  
## <a name="row-layout"></a>行布局

每行的格式如下所示：
  
|**数值数据**|**字节数**|
|:-----|:-----|
|属性数量  <br/> |4  <br/> |
|属性  <br/> |变量  <br/> |
   
属性数量将标识二进制流序列的下一部分中有多少属性。
  
## <a name="property-layout"></a>属性布局

每个属性的格式如下所示：
  
|**数值数据**|**字节数**|
|:-----|:-----|
|属性标记  <br/> |4  <br/> |
|保留数据  <br/> |4  <br/> |
|属性值联合  <br/> ||
|数值数据  <br/> |0 或变量（具体取决于属性标记）  <br/> |
   
## <a name="interpreting-the-property-value"></a>解释属性值

属性值联合和数值数据将基于属性块的前 4 个字节中的属性标记进行解释。 此属性标记的格式与 MAPI 属性标记的格式相同。 属性标记的 0 至 15 位是属性的类型。 16 至 31 位是属性的标识符。 属性类型确定应如何读取属性的其余部分。
  
## <a name="static-value"></a>静态值

某些属性没有数值数据，仅在联合中有数据。 以下属性类型（来自属性标记）可解释 8 个字节的属性联合数据，如下所示：
  
|**属性类型**|**属性联合解释**|
|:-----|:-----|
|PT_I2  <br/> |short int  <br/> |
|PT_LONG  <br/> |long  <br/> |
|PT_R4  <br/> |float  <br/> |
|PT_DOUBLE  <br/> |double  <br/> |
|PT_BOOLEAN  <br/> |short int  <br/> |
|PT_SYSTIME  <br/> |FILETIME  <br/> |
|PT_I8  <br/> |LARGE_INTEGER  <br/> |
   
## <a name="dynamic-values"></a>动态值

其他属性具有在包含属性标记、保留数据和属性值联合的前 16 个字节之后的数值数据块中的数据。 与静态值不同，存储在 8 个字节属性值联合中的数据与读取无关。 写入时，请确保使用某些内容填充这 8 个字节。 但是，这 8 个字节的内容并不重要。 在动态值中，属性标记的类型确定如何解释数值数据。
  
PT_STRING8 
  
|**数值数据**|**字节数**|
|:-----|:-----|
|字节数量 n  <br/> |4  <br/> |
|解释为 ANSI 字符串（包括 NULL 终止符）的字节  <br/> |n  <br/> |
   
PT_CLSID
  
|**数值数据**|**字节数**|
|:-----|:-----|
|解释为 GUID 的字节  <br/> |16  <br/> |
|||
   
PT_BINARY 
  
|**数值数据**|**字节数**|
|:-----|:-----|
|字节数量 n  <br/> |4  <br/> |
|解释为字节数组的字节  <br/> |n  <br/> |
   
PT_ERROR
  
|**数值数据**|**字节数**|
|:-----|:-----|
|字节数量 n  <br/> |4  <br/> |
|解释为字节数组的字节  <br/> |n  <br/> |
   
PT_MV_BINARY
  
|**数值数据**|**字节数**|
|:-----|:-----|
|二进制数组数量 X  <br/> |4  <br/> |
|包含 X 个二进制数组的一串字节。 每个数组应完全解释为 PT_BINARY 字节串。  <br/> |变量  <br/> |
   
PT_MV_STRING8 (Outlook 2007, Outlook 2010, and Outlook 2013)
  
|**数值数据**|**字节数**|
|:-----|:-----|
|ANSI 字符串数量 X  <br/> |4  <br/> |
|包含 X 个 ANSI 字符串的一串字节。 每个字符串应完全解释为 PT_STRING8 字节串。  <br/> |变量  <br/> |
   
PT_MV_UNICODE (Outlook 2007, Outlook 2010, Outlook 2013)
  
|**数值数据**|**字节数**|
|:-----|:-----|
|UNICODE 字符串数量 X  <br/> |4  <br/> |
|包含 X 个 UNICODE 字符串的一串字节。 每个数组应完全解释为 PT_UNICODE 字节串。  <br/> |变量  <br/> |
   
## <a name="significant-properties"></a>重要属性

如本主题前面所述，表示属性的二进制块具有与通讯簿收件人的属性对应的属性标记。 对于此处未列出的属性，可以在 http://msdn.microsoft.com/en-us/library/cc433490(EXCHG.80).aspx 查找属性说明。
  
|**属性名称**|**属性标记**|**说明（请参阅 MSDN 获取详细信息）**|
|:-----|:-----|:-----|
|PR_NICK_NAME_W（不在收件人上传输，仅特定于自动完成流）  <br/> |0x6001001f  <br/> |此属性必须位于每个收件人行中的首位。 它在功能上作为收件人行的密钥标识符。  <br/> |
|PR_ENTRYID  <br/> |0x0FFF0102  <br/> |收件人的通讯簿条目标识符。  <br/> |
|PR_DISPLAY_NAME_W  <br/> |0x3001001F  <br/> |收件人的显示名称。  <br/> |
|PR_EMAIL_ADDRESS_W  <br/> |0x3003001F  <br/> |收件人的电子邮件地址（例如 johndoe@contoso.com 或 /o=Contoso/OU=Foo/cn=Recipients/cn=johndoe）  <br/> |
|PR_ADDRTYPE_W  <br/> |0x3002001F  <br/> |收件人的地址类型（例如 SMTP 或 EX）。  <br/> |
|PR_SEARCH_KEY  <br/> |0x300B0102  <br/> |收件人的 MAPI 搜索关键字。  <br/> |
|PR_SMTP_ADDRESS_W  <br/> |0x39FE001f  <br/> |收件人的 SMTP 地址。  <br/> |
|PR_DROPDOWN_DISPLAY_NAME_W（不在收件人上传输，仅特定于自动完成流）  <br/> |0X6003001f  <br/> |显示在自动完成列表中的显示字符串。  <br/> |
|PR_NICK_NAME_WEIGHT（不在收件人上传输，仅特定于自动完成流）  <br/> |0x60040003  <br/> |此自动完成条目的权重。 权重用于确定匹配自动完成列表时自动完成条目发生的顺序。 具有较高权重的条目将显示在具有较低权重的条目前面。 完整的自动完成列表按此属性排序。 权重会随着时间的推移逐渐减少，并在用户向此收件人发送电子邮件时增加。 有关此属性的详细信息，请参阅本主题后面的说明。  <br/> |
   
PR_NICK_NAME_WEIGHT
  
自动完成流中的行集按 PR_NICK_NAME_WEIGHT 属性以降序顺序进行排序，并且自动完成流应始终保留此排序特征。 因此，对行的权重的任何更改也应确保行的位置维护整个行集的排序顺序。 应将行集的任何添加项插入到正确的位置以维护该排序顺序。
  
此权重的最小值为 0x1，最大值为 LONG_MAX。 权重的任何其他值都被视为无效。
  
当 Outlook 2007 向收件人发送邮件或解析收件人时，它会将该收件人的权重增加 0x2000。
  

