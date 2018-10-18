---
<span data-ttu-id="71922-101"><<<<<<< 标头标题： 项目属性 (ADO) TOCTitle： 项目属性 (ADO) === 标题： Item 属性 (ADO) TOCTitle: Item 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="71922-101"><<<<<<< HEAD title: Item Property (ADO) TOCTitle: Item Property (ADO) ======= title: Item property (ADO) TOCTitle: Item property (ADO)</span></span>
>>>>>>> <span data-ttu-id="71922-102">母版页 ms:assetid: 793c305f-0e5b-a529-e21f-b7ab0843ed49 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249499(v=office.15) ms:contentKeyID: 48545767 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="71922-102">master ms:assetid: 793c305f-0e5b-a529-e21f-b7ab0843ed49 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249499(v=office.15) ms:contentKeyID: 48545767 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="71922-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="71922-103"><<<<<<< HEAD</span></span>
# <a name="item-property-ado"></a><span data-ttu-id="71922-104">Item 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="71922-104">Item Property (ADO)</span></span>
=======
# <a name="item-property-ado"></a><span data-ttu-id="71922-105">Item 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="71922-105">Item property (ADO)</span></span>
>>>>>>> <span data-ttu-id="71922-106">master</span><span class="sxs-lookup"><span data-stu-id="71922-106">master</span></span>

<span data-ttu-id="71922-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="71922-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="71922-108">按名称或序号指示集合的特定成员。</span><span class="sxs-lookup"><span data-stu-id="71922-108">Indicates a specific member of a collection, by name or ordinal number.</span></span>

## <a name="syntax"></a><span data-ttu-id="71922-109">语法</span><span class="sxs-lookup"><span data-stu-id="71922-109">Syntax</span></span>

<span data-ttu-id="71922-110">将*对象*设置 = *集合*。Item (Index)</span><span class="sxs-lookup"><span data-stu-id="71922-110">Set*object* = *collection*.Item ( Index )</span></span>

<span data-ttu-id="71922-111"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="71922-111"><<<<<<< HEAD</span></span>
## <a name="return-value"></a><span data-ttu-id="71922-112">返回值</span><span class="sxs-lookup"><span data-stu-id="71922-112">Return Value</span></span>
=======
## <a name="return-value"></a><span data-ttu-id="71922-113">返回值</span><span class="sxs-lookup"><span data-stu-id="71922-113">Return value</span></span>
>>>>>>> <span data-ttu-id="71922-114">master</span><span class="sxs-lookup"><span data-stu-id="71922-114">master</span></span>

<span data-ttu-id="71922-115">返回对象引用。</span><span class="sxs-lookup"><span data-stu-id="71922-115">Returns an object reference.</span></span>

## <a name="parameters"></a><span data-ttu-id="71922-116">参数</span><span class="sxs-lookup"><span data-stu-id="71922-116">Parameters</span></span>

- <span data-ttu-id="71922-117">*Index*</span><span class="sxs-lookup"><span data-stu-id="71922-117">*Index*</span></span>

- <span data-ttu-id="71922-118">一个 **Variant** 表达式，其值为集合中对象的名称或序号。</span><span class="sxs-lookup"><span data-stu-id="71922-118">A **Variant** expression that evaluates either to the name or to the ordinal number of an object in a collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="71922-119">备注</span><span class="sxs-lookup"><span data-stu-id="71922-119">Remarks</span></span>

<span data-ttu-id="71922-120">使用 **Item** 属性可返回集合中的特定对象。</span><span class="sxs-lookup"><span data-stu-id="71922-120">Use the **Item** property to return a specific object in a collection.</span></span> <span data-ttu-id="71922-121">如果**项目**找不到对象对应于*Index*参数集合中，将导致出错。</span><span class="sxs-lookup"><span data-stu-id="71922-121">If **Item** cannot find an object in the collection corresponding to the *Index* argument, an error occurs.</span></span> <span data-ttu-id="71922-122">此外，有些集合不支持命名对象；对于这些集合，必须使用序号引用。</span><span class="sxs-lookup"><span data-stu-id="71922-122">Also, some collections don't support named objects; for these collections, you must use ordinal number references.</span></span>

<span data-ttu-id="71922-123">**Item** 属性是所有集合的默认属性；因此，以下语法格式可互换：</span><span class="sxs-lookup"><span data-stu-id="71922-123">The **Item** property is the default property for all collections; therefore, the following syntax forms are interchangeable:</span></span>

```vb
    collection.Item (Index)
    collection (Index)
```
