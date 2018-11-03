---
title: Open 方法（ADO 流）
TOCTitle: Open method (ADO Stream)
ms:assetid: fa2e6aaa-e9f5-009c-f3a0-050a00abf9b0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250275(v=office.15)
ms:contentKeyID: 48548833
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: cc0f12e05e65dd24b73dfcf5702fbe09169ba397
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944834"
---
# <a name="open-method-ado-stream"></a><span data-ttu-id="a4452-102">Open 方法（ADO 流）</span><span class="sxs-lookup"><span data-stu-id="a4452-102">Open method (ADO Stream)</span></span>


<span data-ttu-id="a4452-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="a4452-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="a4452-104">用于打开 [Stream](stream-object-ado.md) 对象，以操作二进制数据流或文本数据流。</span><span class="sxs-lookup"><span data-stu-id="a4452-104">Opens a [Stream](stream-object-ado.md) object to manipulate streams of binary or text data.</span></span>

## <a name="syntax"></a><span data-ttu-id="a4452-105">语法</span><span class="sxs-lookup"><span data-stu-id="a4452-105">Syntax</span></span>

<span data-ttu-id="a4452-106">*流*。</span><span class="sxs-lookup"><span data-stu-id="a4452-106">*Stream*.</span></span> <span data-ttu-id="a4452-107">打开*源*、*模式*、 *OpenOptions*、*用户名*、*密码*</span><span class="sxs-lookup"><span data-stu-id="a4452-107">Open *Source*, *Mode*, *OpenOptions*, *UserName*, *Password*</span></span>

## <a name="parameters"></a><span data-ttu-id="a4452-108">参数</span><span class="sxs-lookup"><span data-stu-id="a4452-108">Parameters</span></span>

  - <span data-ttu-id="a4452-109">*Source*</span><span class="sxs-lookup"><span data-stu-id="a4452-109">*Source*</span></span>

  - <span data-ttu-id="a4452-110">可选。</span><span class="sxs-lookup"><span data-stu-id="a4452-110">Optional.</span></span> <span data-ttu-id="a4452-111">**变量型** 值，用于指定 **Stream** 的数据源。</span><span class="sxs-lookup"><span data-stu-id="a4452-111">A **Variant** value that specifies the source of data for the **Stream**.</span></span> <span data-ttu-id="a4452-112">*源*可能包含指向已知树结构中，如电子邮件或文件系统中的现有节点的绝对 URL 字符串。</span><span class="sxs-lookup"><span data-stu-id="a4452-112">*Source* may contain an absolute URL string that points to an existing node in a well-known tree structure, like an e-mail or file system.</span></span> <span data-ttu-id="a4452-113">应使用 URL 关键字指定 URL ("URL =*方案*://*服务器*/*文件夹*")。</span><span class="sxs-lookup"><span data-stu-id="a4452-113">A URL should be specified using the URL keyword ("URL=*scheme*://*server*/*folder*").</span></span> <span data-ttu-id="a4452-114">另外， *Source*可以包含对打开与**记录**相关联的默认流已打开[Record](record-object-ado.md)对象的引用。</span><span class="sxs-lookup"><span data-stu-id="a4452-114">Alternately, *Source* may contain a reference to an already open [Record](record-object-ado.md) object, which opens the default stream associated with the **Record**.</span></span> <span data-ttu-id="a4452-115">如果未指定*源*，**流**实例化和打开，默认情况下与没有基础源关联。</span><span class="sxs-lookup"><span data-stu-id="a4452-115">If *Source* is not specified, a **Stream** is instantiated and opened, associated with no underlying source by default.</span></span> <span data-ttu-id="a4452-116">有关 URL 架构及其关联提供程序的详细信息，请参阅 [绝对 URL 和相对 URL](absolute-and-relative-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="a4452-116">For more information about URL schemes and their associated providers, see [Absolute and Relative URLs](absolute-and-relative-urls.md).</span></span>

  - <span data-ttu-id="a4452-117">*Mode*</span><span class="sxs-lookup"><span data-stu-id="a4452-117">*Mode*</span></span>

  - <span data-ttu-id="a4452-118">可选。</span><span class="sxs-lookup"><span data-stu-id="a4452-118">Optional.</span></span> <span data-ttu-id="a4452-119">指定产生的**Stream**的访问模式[ConnectModeEnum](connectmodeenum.md)值 (例如，读/写或只读)。</span><span class="sxs-lookup"><span data-stu-id="a4452-119">A [ConnectModeEnum](connectmodeenum.md) value that specifies the access mode for the resultant **Stream** (for example, read/write or read-only).</span></span> <span data-ttu-id="a4452-120">默认值为**adModeUnknown**。</span><span class="sxs-lookup"><span data-stu-id="a4452-120">Default value is **adModeUnknown**.</span></span> <span data-ttu-id="a4452-121">请参阅有关访问模式的详细信息的[Mode](mode-property-ado.md)属性。</span><span class="sxs-lookup"><span data-stu-id="a4452-121">See the [Mode](mode-property-ado.md) property for more information about access modes.</span></span> <span data-ttu-id="a4452-122">如果未指定*模式*，它被继承的源对象。</span><span class="sxs-lookup"><span data-stu-id="a4452-122">If *Mode* is not specified, it is inherited by the source object.</span></span> <span data-ttu-id="a4452-123">例如，如果**记录**的源在只读模式打开，**流**将还打开只读模式中默认情况下。</span><span class="sxs-lookup"><span data-stu-id="a4452-123">For example, if the source **Record** is opened in read-only mode, the **Stream** will also be opened in read-only mode by default.</span></span>

  - <span data-ttu-id="a4452-124">*OpenOptions*</span><span class="sxs-lookup"><span data-stu-id="a4452-124">*OpenOptions*</span></span>

  - <span data-ttu-id="a4452-p104">可选。[StreamOpenOptionsEnum](streamopenoptionsenum.md) 值。默认值为 **adOpenStreamUnspecified** 。</span><span class="sxs-lookup"><span data-stu-id="a4452-p104">Optional. A [StreamOpenOptionsEnum](streamopenoptionsenum.md) value. Default value is **adOpenStreamUnspecified**.</span></span>

  - <span data-ttu-id="a4452-128">*UserName*</span><span class="sxs-lookup"><span data-stu-id="a4452-128">*UserName*</span></span>

  - <span data-ttu-id="a4452-p105">可选。包含用户标识的 **字符串型** 值，如果需要，将访问 **Stream** 对象。</span><span class="sxs-lookup"><span data-stu-id="a4452-p105">Optional. A **String** value that contains the user identification that, if needed, accesses the **Stream** object.</span></span>

  - <span data-ttu-id="a4452-131">*Password*</span><span class="sxs-lookup"><span data-stu-id="a4452-131">*Password*</span></span>

  - <span data-ttu-id="a4452-p106">可选。包含密码的 **字符串型** 值，如果需要，将访问 **Stream** 对象。</span><span class="sxs-lookup"><span data-stu-id="a4452-p106">Optional. A **String** value that contains the password that, if needed, accesses the **Stream** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="a4452-134">备注</span><span class="sxs-lookup"><span data-stu-id="a4452-134">Remarks</span></span>

<span data-ttu-id="a4452-135">作为源参数，*用户 Id*和*密码*参数中传递**Record**对象时不使用**Record**对象访问是已可用。</span><span class="sxs-lookup"><span data-stu-id="a4452-135">When a **Record** object is passed in as the source parameter, the *UserID* and *Password* parameters are not used because access to the **Record** object is already available.</span></span> <span data-ttu-id="a4452-136">同样， **Record**对象[模式](mode-property-ado.md)被转移到**Stream**对象。如果未指定*源*，打开的**流**不包含数据和的[大小](https://msdn.microsoft.com/library/jj250128\(v=office.15\))为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="a4452-136">Similarly, the [Mode](mode-property-ado.md) of the **Record** object is transferred to the **Stream** object.When *Source* is not specified, the **Stream** opened contains no data and has a [Size](https://msdn.microsoft.com/library/jj250128\(v=office.15\)) of zero (0).</span></span> <span data-ttu-id="a4452-137">若要避免丢失**流**关闭时，会写入此**流**的任何数据，请使用[CopyTo](copyto-method-ado.md)或[SaveToFile](savetofile-method-ado.md)方法保存**流**或将其保存到另一个内存位置。</span><span class="sxs-lookup"><span data-stu-id="a4452-137">To avoid losing any data that is written to this **Stream** when the **Stream** is closed, save the **Stream** with the [CopyTo](copyto-method-ado.md) or [SaveToFile](savetofile-method-ado.md) methods, or save it to another memory location.</span></span>

<span data-ttu-id="a4452-138">**AdOpenStreamFromRecord** *OpenOptions*值标识*源*参数设置为已打开的**Record**对象的内容。</span><span class="sxs-lookup"><span data-stu-id="a4452-138">An *OpenOptions* value of **adOpenStreamFromRecord** identifies the contents of the *Source* parameter to be an already open **Record** object.</span></span> <span data-ttu-id="a4452-139">默认行为是*源*视为直接指向树状结构中，例如文件中的节点的 URL。</span><span class="sxs-lookup"><span data-stu-id="a4452-139">The default behavior is to treat *Source* as a URL that points directly to a node in a tree structure, such as a file.</span></span> <span data-ttu-id="a4452-140">将打开与该节点关联的默认流。</span><span class="sxs-lookup"><span data-stu-id="a4452-140">The default stream associated with that node is opened.</span></span>

<span data-ttu-id="a4452-p109">在 **Stream** 未打开时，可以读取 **Stream** 的所有只读属性。如果 **Stream** 是异步打开的，则所有后续操作（检查 [State 属性 (ADO)](state-property-ado.md) 和其他只读属性的操作除外）将被阻止，直到 **Open** 操作完成。</span><span class="sxs-lookup"><span data-stu-id="a4452-p109">While the **Stream** is not open, it is possible to read all the read-only properties of the **Stream**. If a **Stream** is opened asynchronously, all subsequent operations (other than checking the [State](state-property-ado.md) and other read-only properties) are blocked until the **Open** operation is completed.</span></span>

<span data-ttu-id="a4452-p110">除了上面讨论的选项外，如果不指定 *Source*，可以在内存中只实例化 **Stream** 对象，而不将其与基础源关联。只需使用 [Write](write-method-ado.md) 或 [WriteText](writetext-method-ado.md) 将二进制数据或文本数据写入 **Stream**，或者使用 [LoadFromFile](loadfromfile-method-ado.md) 从文件中加载数据，便可以动态地向流添加数据。</span><span class="sxs-lookup"><span data-stu-id="a4452-p110">In addition to the options discussed above, by not specifying *Source*, you can simply instantiate a **Stream** object in memory without associating it with an underlying source. You can dynamically add data to the stream simply by writing binary or text data to the **Stream** with [Write](write-method-ado.md) or [WriteText](writetext-method-ado.md), or by loading data from a file with [LoadFromFile](loadfromfile-method-ado.md).</span></span>

