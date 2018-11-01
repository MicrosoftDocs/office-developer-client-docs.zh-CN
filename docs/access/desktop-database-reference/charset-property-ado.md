---
title: Charset 属性 (ADO)
TOCTitle: Charset property (ADO)
ms:assetid: 454f664e-6d62-eec9-487d-882c2f9503b0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249213(v=office.15)
ms:contentKeyID: 48544551
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 46d9016e84b507526fa36202169f532e9ee7d738
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25887787"
---
# <a name="charset-property-ado"></a><span data-ttu-id="866dc-102">Charset 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="866dc-102">Charset property (ADO)</span></span>


<span data-ttu-id="866dc-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="866dc-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="866dc-104">指示一个字符集，文本 [Stream](stream-object-ado.md) 的内容应转换为该字符集，以存储在 Stream 对象内部缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="866dc-104">Indicates the character set into which the contents of a text [Stream](stream-object-ado.md) should be translated for storage in the Stream objects internal buffer.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="866dc-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="866dc-105">Settings and return values</span></span>

<span data-ttu-id="866dc-106">设置或返回一个 **String** 值，该值指定 **Stream** 的内容将要转换为的字符集。</span><span class="sxs-lookup"><span data-stu-id="866dc-106">Sets or returns a **String** value that specifies the character set into which the contents of the **Stream** will be translated.</span></span> <span data-ttu-id="866dc-107">默认值为"Unicode"。</span><span class="sxs-lookup"><span data-stu-id="866dc-107">The default value is "Unicode".</span></span> <span data-ttu-id="866dc-108">允许的值为作为 Internet 字符集字符串通过接口传递的常见字符串（例如，"iso-8859-1"、"Windows-1252"等）。</span><span class="sxs-lookup"><span data-stu-id="866dc-108">Allowed values are typical strings passed over the interface as Internet character set strings (for example, "iso-8859-1", "Windows-1252", etc.).</span></span> <span data-ttu-id="866dc-109">由系统已知的字符串集列表，请参阅 HKEY 的子项\_类\_根\\MIME\\数据库\\Windows 注册表中的字符集。</span><span class="sxs-lookup"><span data-stu-id="866dc-109">For a list of the character set strings that is known by a system, see the subkeys of HKEY\_CLASSES\_ROOT\\MIME\\Database\\Charset in the Windows Registry.</span></span>

## <a name="remarks"></a><span data-ttu-id="866dc-110">备注</span><span class="sxs-lookup"><span data-stu-id="866dc-110">Remarks</span></span>

<span data-ttu-id="866dc-p102">在文本 **Stream** 对象中，文本数据是采用 **Charset** 属性指定的字符集存储的。默认值为"Unicode"。 **Charset** 属性用于对传入 **Stream** 或从 **Stream** 传出的数据进行转换。例如，如果 **Stream** 包含 ISO-8859-1 数据，而又要将该数据复制到 BSTR 中， **Stream** 对象会将该数据转换为 Unicode。反之亦然。</span><span class="sxs-lookup"><span data-stu-id="866dc-p102">In a text **Stream** object, text data is stored in the character set specified by the **Charset** property. The default is Unicode. The **Charset** property is used for converting data going into the **Stream** or coming out of the **Stream**. For example, if the **Stream** contains ISO-8859-1 data and that data is copied to a BSTR, the **Stream** object will convert the data to Unicode. The reverse is also true.</span></span>

<span data-ttu-id="866dc-116">对于打开的 **Stream** ，当前的 [Position](position-property-ado.md) 值必须位于 **Stream** 的开始处 (0)，才能设置 **Charset** 。</span><span class="sxs-lookup"><span data-stu-id="866dc-116">For an open **Stream**, the current [Position](position-property-ado.md) must be at the beginning of the **Stream** (0) to be able to set **Charset**.</span></span>

<span data-ttu-id="866dc-p103">**Charset** 仅与文本 **Stream** 对象（[Type](type-property-ado-stream.md) 为 **adTypeText**）一起使用。如果 **Type** 为 **adTypeBinary**，则忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="866dc-p103">**Charset** is used only with text **Stream** objects ([Type](type-property-ado-stream.md) is **adTypeText**). This property is ignored if **Type** is **adTypeBinary**.</span></span>

