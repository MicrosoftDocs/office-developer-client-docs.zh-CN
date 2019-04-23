---
title: Open 方法（ADO 流）
TOCTitle: Open method (ADO Stream)
ms:assetid: fa2e6aaa-e9f5-009c-f3a0-050a00abf9b0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250275(v=office.15)
ms:contentKeyID: 48548833
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3a943209ce329d59fb4846ed18fd008bc45803da
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288383"
---
# <a name="open-method-ado-stream"></a><span data-ttu-id="b9e1a-102">Open 方法（ADO 流）</span><span class="sxs-lookup"><span data-stu-id="b9e1a-102">Open method (ADO Stream)</span></span>


<span data-ttu-id="b9e1a-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="b9e1a-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="b9e1a-104">用于打开 [Stream](stream-object-ado.md) 对象，以操作二进制数据流或文本数据流。</span><span class="sxs-lookup"><span data-stu-id="b9e1a-104">Opens a [Stream](stream-object-ado.md) object to manipulate streams of binary or text data.</span></span>

## <a name="syntax"></a><span data-ttu-id="b9e1a-105">语法</span><span class="sxs-lookup"><span data-stu-id="b9e1a-105">Syntax</span></span>

<span data-ttu-id="b9e1a-106">*Stream*。</span><span class="sxs-lookup"><span data-stu-id="b9e1a-106">*Stream*.</span></span> <span data-ttu-id="b9e1a-107">开放*源代码*、*模式*、 *OpenOptions*、*用户名*、*密码*</span><span class="sxs-lookup"><span data-stu-id="b9e1a-107">Open *Source*, *Mode*, *OpenOptions*, *UserName*, *Password*</span></span>

## <a name="parameters"></a><span data-ttu-id="b9e1a-108">参数</span><span class="sxs-lookup"><span data-stu-id="b9e1a-108">Parameters</span></span>

|<span data-ttu-id="b9e1a-109">参数</span><span class="sxs-lookup"><span data-stu-id="b9e1a-109">Parameter</span></span>|<span data-ttu-id="b9e1a-110">描述</span><span class="sxs-lookup"><span data-stu-id="b9e1a-110">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="b9e1a-111">*Source*</span><span class="sxs-lookup"><span data-stu-id="b9e1a-111">*Source*</span></span> |<span data-ttu-id="b9e1a-112">可选。</span><span class="sxs-lookup"><span data-stu-id="b9e1a-112">Optional.</span></span> <span data-ttu-id="b9e1a-113">**变量型** 值，用于指定 **Stream** 的数据源。</span><span class="sxs-lookup"><span data-stu-id="b9e1a-113">A **Variant** value that specifies the source of data for the **Stream**.</span></span> <span data-ttu-id="b9e1a-114">*Source*可以包含指向已知树结构 (如电子邮件或文件系统) 中的现有节点的绝对 URL 字符串。</span><span class="sxs-lookup"><span data-stu-id="b9e1a-114">*Source* may contain an absolute URL string that points to an existing node in a well-known tree structure, like an email or file system.</span></span> <span data-ttu-id="b9e1a-115">应使用 url 关键字 ("url =*方案*:///*服务器*/*文件夹*") 指定 url。</span><span class="sxs-lookup"><span data-stu-id="b9e1a-115">A URL should be specified using the URL keyword ("URL=*scheme*://*server*/*folder*").</span></span> <span data-ttu-id="b9e1a-116">*Source* 也可以包含对已打开的 [Record](record-object-ado.md) 对象的引用，该引用打开与 **Record** 关联的默认流。</span><span class="sxs-lookup"><span data-stu-id="b9e1a-116">Alternately, *Source* may contain a reference to an already open [Record](record-object-ado.md) object, which opens the default stream associated with the **Record**.</span></span> <span data-ttu-id="b9e1a-117">如果未指定 *Source*，那么将实例化并打开 **Stream**，且该流默认情况下不与任何基础源关联。</span><span class="sxs-lookup"><span data-stu-id="b9e1a-117">If *Source* is not specified, a **Stream** is instantiated and opened, associated with no underlying source by default.</span></span> <span data-ttu-id="b9e1a-118">有关 URL 方案及其关联提供程序的详细信息, 请参阅[绝对和相对 url](absolute-and-relative-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="b9e1a-118">For more information about URL schemes and their associated providers, see [Absolute and relative URLs](absolute-and-relative-urls.md).</span></span>|
|<span data-ttu-id="b9e1a-119">*Mode*</span><span class="sxs-lookup"><span data-stu-id="b9e1a-119">*Mode*</span></span> |<span data-ttu-id="b9e1a-p103">可选。[ConnectModeEnum](connectmodeenum.md) 值，用于指定生成的 **Stream** 的访问模式（如读/写或只读）。默认值为 **adModeUnknown**。有关访问模式的详细信息，请参阅 [Mode](mode-property-ado.md) 属性。如果未指定 *Mode*，则从源对象继承模式。例如，如果以只读模式打开源 **Record**，则默认情况下 **Stream** 也将以只读模式打开。</span><span class="sxs-lookup"><span data-stu-id="b9e1a-p103">Optional. A [ConnectModeEnum](connectmodeenum.md) value that specifies the access mode for the resultant **Stream** (for example, read/write or read-only). Default value is **adModeUnknown**. See the [Mode](mode-property-ado.md) property for more information about access modes. If *Mode* is not specified, it is inherited by the source object. For example, if the source **Record** is opened in read-only mode, the **Stream** will also be opened in read-only mode by default.</span></span>|
|<span data-ttu-id="b9e1a-126">*OpenOptions*</span><span class="sxs-lookup"><span data-stu-id="b9e1a-126">*OpenOptions*</span></span> |<span data-ttu-id="b9e1a-p104">可选。[StreamOpenOptionsEnum](streamopenoptionsenum.md) 值。默认值为 **adOpenStreamUnspecified** 。</span><span class="sxs-lookup"><span data-stu-id="b9e1a-p104">Optional. A [StreamOpenOptionsEnum](streamopenoptionsenum.md) value. Default value is **adOpenStreamUnspecified**.</span></span>|
|<span data-ttu-id="b9e1a-130">*UserName*</span><span class="sxs-lookup"><span data-stu-id="b9e1a-130">*UserName*</span></span> |<span data-ttu-id="b9e1a-p105">可选。包含用户标识的 **字符串型** 值，如果需要，将访问 **Stream** 对象。</span><span class="sxs-lookup"><span data-stu-id="b9e1a-p105">Optional. A **String** value that contains the user identification that, if needed, accesses the **Stream** object.</span></span>|
|<span data-ttu-id="b9e1a-133">*Password*</span><span class="sxs-lookup"><span data-stu-id="b9e1a-133">*Password*</span></span> |<span data-ttu-id="b9e1a-p106">可选。包含密码的 **字符串型** 值，如果需要，将访问 **Stream** 对象。</span><span class="sxs-lookup"><span data-stu-id="b9e1a-p106">Optional. A **String** value that contains the password that, if needed, accesses the **Stream** object.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b9e1a-136">注解</span><span class="sxs-lookup"><span data-stu-id="b9e1a-136">Remarks</span></span>

<span data-ttu-id="b9e1a-p107">将 **Record** 对象作为源参数传入时，不使用 *UserID* 和 *Password* 参数，因为已具有对 **Record** 对象的访问权限。同样，**Record** 对象的 [Mode 属性 (ADO)](mode-property-ado.md) 传送到 **Stream** 对象。如果未指定 *Source*，则打开的 **Stream** 不包含任何数据，且 [Size 属性 (ADO Stream)](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/size-property-ado-stream) 为零 (0)。若要避免在关闭 **Stream** 时丢失写入该 **Stream** 的任何数据，请使用 [CopyTo](copyto-method-ado.md) 或 [SaveToFile](savetofile-method-ado.md) 方法来保存 **Stream**，或者将其保存到其他内存位置。</span><span class="sxs-lookup"><span data-stu-id="b9e1a-p107">When a **Record** object is passed in as the source parameter, the *UserID* and *Password* parameters are not used because access to the **Record** object is already available. Similarly, the [Mode](mode-property-ado.md) of the **Record** object is transferred to the **Stream** object.When *Source* is not specified, the **Stream** opened contains no data and has a [Size](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/size-property-ado-stream) of zero (0). To avoid losing any data that is written to this **Stream** when the **Stream** is closed, save the **Stream** with the [CopyTo](copyto-method-ado.md) or [SaveToFile](savetofile-method-ado.md) methods, or save it to another memory location.</span></span>

<span data-ttu-id="b9e1a-p108">值为 **adOpenStreamFromRecord** 的 *OpenOptions* 将 *Source* 参数的内容标识为已打开的 **Record** 对象。默认行为是将 *Source* 视为直接指向树结构中的节点（如文件）的 URL。将打开与该节点关联的默认流。</span><span class="sxs-lookup"><span data-stu-id="b9e1a-p108">An *OpenOptions* value of **adOpenStreamFromRecord** identifies the contents of the *Source* parameter to be an already open **Record** object. The default behavior is to treat *Source* as a URL that points directly to a node in a tree structure, such as a file. The default stream associated with that node is opened.</span></span>

<span data-ttu-id="b9e1a-p109">在 **Stream** 未打开时，可以读取 **Stream** 的所有只读属性。如果 **Stream** 是异步打开的，则所有后续操作（检查 [State 属性 (ADO)](state-property-ado.md) 和其他只读属性的操作除外）将被阻止，直到 **Open** 操作完成。</span><span class="sxs-lookup"><span data-stu-id="b9e1a-p109">While the **Stream** is not open, it is possible to read all the read-only properties of the **Stream**. If a **Stream** is opened asynchronously, all subsequent operations (other than checking the [State](state-property-ado.md) and other read-only properties) are blocked until the **Open** operation is completed.</span></span>

<span data-ttu-id="b9e1a-p110">除了上面讨论的选项外，如果不指定 *Source*，可以在内存中只实例化 **Stream** 对象，而不将其与基础源关联。只需使用 [Write](write-method-ado.md) 或 [WriteText](writetext-method-ado.md) 将二进制数据或文本数据写入 **Stream**，或者使用 [LoadFromFile](loadfromfile-method-ado.md) 从文件中加载数据，便可以动态地向流添加数据。</span><span class="sxs-lookup"><span data-stu-id="b9e1a-p110">In addition to the options discussed above, by not specifying *Source*, you can simply instantiate a **Stream** object in memory without associating it with an underlying source. You can dynamically add data to the stream simply by writing binary or text data to the **Stream** with [Write](write-method-ado.md) or [WriteText](writetext-method-ado.md), or by loading data from a file with [LoadFromFile](loadfromfile-method-ado.md).</span></span>

