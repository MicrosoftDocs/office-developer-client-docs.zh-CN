---
title: 记忆式键入流
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: d4f380fa-2ed9-4c7c-9ef3-b32f8409f657
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 7fc1fae4ed648d59c273b20ced247f6d20e01a6f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774600"
---
# <a name="autocomplete-stream"></a>记忆式键入流

  
  
**适用于**： Outlook 
  
除了了解 Microsoft Outlook 与记忆式键入数据流的交互方式，您还必须了解记忆式键入 stream 的二进制格式。
  
记忆式键入流是一组收件人属性行的保存为二进制流以及仅由 Microsoft Outlook 2013、 Microsoft Outlook 2010、 Microsoft Office Outlook 2007 中，和 Microsoft Outlook 2003 一些记帐元数据。 元数据是与记忆式键入流 Outlook 交互相关，因此第三方必须保留它们保存修改后的记忆式键入流时在每个元数据块新增。 换句话说，第三方应修改仅二进制格式的行集一部分和保留内容已在记忆式键入流的元数据块。
  
## <a name="stream-visualization"></a>流可视化

记忆式键入流的高级布局是，如下所示：
  
元数据 （4 个字节）
  
主版本号 （4 个字节）
  
次要版本号 （4 个字节）
  
行 n （4 个字节） 的数目
  
第一行 （4 个字节） 中的属性 p 的数目
  
属性 1 的属性标记 （4 个字节）
  
属性 1 的保留数据 （4 个字节）
  
1 的属性值 union （8 个字节）
  
1 的属性值数据 （0 或变量字节）
  
… （通过属性 P-1 属性 2）
  
属性 p 的属性标记 （4 个字节）
  
属性 p 的保留数据 （4 个字节）
  
P 的属性值 union （8 个字节）
  
P 的属性值数据 （0 或变量字节）
  
第二行中的属性 q （4 个字节） 的数目
  
… （行 2 的属性）
  
… （通过行 n-1 第 3 行）
  
属性 r 行 n （4 个字节） 中的数目
  
… (行 n's 属性)
  
额外信息字节数 EI （4 个字节）
  
额外信息 （EI 字节）
  
元数据 （8 个字节）
  
二进制结构的示例，请参阅中的二进制示例[Outlook 2003/2007 NK2 文件格式和开发人员的准则。](http://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)
  
## <a name="high-level-layout"></a>高级布局

概括地说，记忆式键入 stream 的布局如下所示：
  
|**值数据**|**字节数**|
|:-----|:-----|
|元数据  <br/> |4  <br/> |
|主版本号  <br/> |4  <br/> |
|次版本号  <br/> |4  <br/> |
|行集  <br/> |变量  <br/> |
|额外信息字节数 EI  <br/> |4  <br/> |
|额外信息  <br/> |EI  <br/> |
|元数据  <br/> |8  <br/> |
   
读取数据时此流，如果的主要版本不同于 12，然后此流不应读取或写入。 记忆式键入 stream 的当前的次要版本是 0，已设置为 0 的额外信息字节数。 如果不同于 0 次要版本，然后将会在需要时读取流读取和写入 stream 时保留的额外信息的信息。 此外需要编写流时保留次要版本。 如果这两个不保留，实例编写的额外信息的 Outlook 会丢失数据。 
  
> [!NOTE]
> 应用程序不必须将自定义数据添加到的额外信息字段或更改次要版本，如旨在支持为格式的 Outlook 扩展; 并不任意第三方扩展此功能。 
  
## <a name="row-set-layout"></a>行集布局

行集布局如下所示： 
  
|**值数据**|**字节数**|
|:-----|:-----|
|行数  <br/> |4  <br/> |
|Rows  <br/> |变量  <br/> |
   
行数标识多少行并非在二进制流序列的下一部分。
  
## <a name="row-layout"></a>行布局

每一行都是以下格式：
  
|**值数据**|**字节数**|
|:-----|:-----|
|属性数  <br/> |4  <br/> |
|属性  <br/> |变量  <br/> |
   
属性数标识多少属性并非在二进制流序列的下一部分。
  
## <a name="property-layout"></a>属性布局

每个属性属于以下格式：
  
|**值数据**|**字节数**|
|:-----|:-----|
|属性标记  <br/> |4  <br/> |
|保留的数据  <br/> |4  <br/> |
|属性值 Union  <br/> ||
|值数据  <br/> |0 或变量 （具体取决于属性标记中）  <br/> |
   
## <a name="interpreting-the-property-value"></a>解释属性值

属性值 Union 和值数据是基于属性块的前 4 个字节中的属性标记解释。 此属性标记是一个 MAPI 属性标记为相同的格式。 0 到 15 属性标记的位是该属性的类型。 通过 31 16 位是该属性的标识符。 属性类型确定应如何读取属性的其余部分。
  
## <a name="static-value"></a>静态值

某些属性没有值数据，只有联合中的数据。 以下属性类型 （其中来自属性标记） 应解释 8 字节属性联合数据，如下所示：
  
|**属性类型**|**Union Interpretation 属性**|
|:-----|:-----|
|PT_I2  <br/> |短 int  <br/> |
|PT_LONG  <br/> |long  <br/> |
|PT_R4  <br/> |float  <br/> |
|PT_DOUBLE  <br/> |double  <br/> |
|PT_BOOLEAN  <br/> |短 int  <br/> |
|PT_SYSTIME  <br/> |FILETIME  <br/> |
|PT_I8  <br/> |LARGE_INTEGER  <br/> |
   
## <a name="dynamic-values"></a>动态值

其他属性值数据块中有数据后属性标记、 保留的数据和属性值 Union 包含第一个 16 字节。 与静态值、 不同的数据的存储在 8 字节属性值 union 上阅读无关。 编写时，请确保您具有某些填充这些 8 个字节。 但是，8 个字节的内容并不重要。 在动态值属性标记的类型确定如何解释数值数据。
  
PT_STRING8 
  
|**值数据**|**字节数**|
|:-----|:-----|
|字节 n 的数目  <br/> |4  <br/> |
|字节被解释为 ANSI 字符串 （包括 NULL 终止符）  <br/> |n  <br/> |
   
PT_CLSID
  
|**值数据**|**字节数**|
|:-----|:-----|
|字节被解释为 GUID  <br/> |16  <br/> |
|||
   
PT_BINARY 
  
|**值数据**|**字节数**|
|:-----|:-----|
|字节 n 的数目  <br/> |4  <br/> |
|字节被解释为一个字节数组  <br/> |n  <br/> |
   
PT_ERROR
  
|**值数据**|**字节数**|
|:-----|:-----|
|字节 n 的数目  <br/> |4  <br/> |
|字节被解释为一个字节数组  <br/> |n  <br/> |
   
PT_MV_BINARY
  
|**值数据**|**字节数**|
|:-----|:-----|
|二进制阵列 X 数  <br/> |4  <br/> |
|一个运行的包含 X 字节二进制数组。 应将每个阵列解释完全一样运行的 PT_BINARY 字节。  <br/> |变量  <br/> |
   
PT_MV_STRING8 （Outlook 2007 和 Outlook 2010 中，Outlook 2013）
  
|**值数据**|**字节数**|
|:-----|:-----|
|ANSI 字符串 X 数  <br/> |4  <br/> |
|一段连续文本的字节，其中包含 X ANSI 字符串。 应将每个字符串解释完全一样运行的 PT_STRING8 字节。  <br/> |变量  <br/> |
   
PT_MV_UNICODE （Outlook 2007、 Outlook 2010 或 Outlook 2013）
  
|**值数据**|**字节数**|
|:-----|:-----|
|UNICODE 字符串 X 数  <br/> |4  <br/> |
|一段连续文本的字节，其中包含 X UNICODE 字符串。 应将每个字符串解释完全一样运行的 PT_UNICODE 字节。  <br/> |变量  <br/> |
   
## <a name="significant-properties"></a>重要的属性

本主题中提到，表示属性的二进制块具有对应的地址簿收件人属性的属性标记。 对于未此处列出的属性，您可以查找属性说明http://msdn.microsoft.com/en-us/library/cc433490(EXCHG.80).aspx。
  
|**属性名**|**属性标记**|**说明 （有关详细信息，请参阅 MSDN）**|
|:-----|:-----|:-----|
|PR_NICK_NAME_W （不在收件人，特定于仅记忆式键入流上传输）  <br/> |0x6001001f  <br/> |此属性必须为每个收件人的行中第一个。 它功能上相当于收件人行的密钥标识符。  <br/> |
|PR_ENTRYID  <br/> |0x0FFF0102  <br/> |收件人地址簿条目标识符。  <br/> |
|PR_DISPLAY_NAME_W  <br/> |0x3001001F  <br/> |收件人的显示名称。  <br/> |
|PR_EMAIL_ADDRESS_W  <br/> |0x3003001F  <br/> |收件人的电子邮件地址 (例如 johndoe@contoso.com 或 /o = Contoso/OU = Foo/cn = Recipients/cn = johndoe)  <br/> |
|PR_ADDRTYPE_W  <br/> |0x3002001F  <br/> |收件人的地址类型 （例如 SMTP 或 EX）。  <br/> |
|PR_SEARCH_KEY  <br/> |0x300B0102  <br/> |收件人的 MAPI 搜索键。  <br/> |
|PR_SMTP_ADDRESS_W  <br/> |0x39FE001f  <br/> |收件人的 SMTP 地址。  <br/> |
|PR_DROPDOWN_DISPLAY_NAME_W （不在收件人，特定于仅记忆式键入流上传输）  <br/> |0X6003001f  <br/> |显示记忆式键入列表中显示字符串。  <br/> |
|PR_NICK_NAME_WEIGHT （不在收件人，特定于仅记忆式键入流上传输）  <br/> |0x60040003  <br/> |此记忆式键入条目的权重。 权重用于确定哪些订单记忆式键入条目时，出现匹配记忆式键入列表。 使用较低的权重项之前将显示具有更高的权重的条目。 完成记忆式键入列表被按此属性。 权重定期减小随着时间的推移，并增加时用户向此收件人发送电子邮件。 请参阅有关此属性的详细信息本主题后面的说明。  <br/> |
   
PR_NICK_NAME_WEIGHT
  
PR_NICK_NAME_WEIGHT 属性按降序顺序排序的记忆式键入流中的行集并记忆式键入流应始终保留此排序的特征。 因此，对某一行的权重的任何更改还应确保行的位置保持整个行集的排序的顺序。 任何行集的新增功能应插入到正确的位置，以维护排序的顺序。
  
此权重的最小值是 0x1，最大值是 LONG_MAX。 权重的任何其他值都被视为无效。
  
当 Outlook 2007 发送到邮件或解析收件人，它将按 0x2000 提升的收件人的权重。
  

