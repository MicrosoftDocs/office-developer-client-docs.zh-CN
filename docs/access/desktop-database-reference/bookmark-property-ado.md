---
<span data-ttu-id="68541-101"><<<<<<< 标头标题： Bookmark 属性 (ADO) TOCTitle: Bookmark 属性 (ADO) === 标题： Bookmark 属性 (ADO) TOCTitle: Bookmark 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="68541-101"><<<<<<< HEAD title: Bookmark Property (ADO) TOCTitle: Bookmark Property (ADO) ======= title: Bookmark property (ADO) TOCTitle: Bookmark property (ADO)</span></span>
>>>>>>> <span data-ttu-id="68541-102">母版页 ms:assetid: 101b2ce1-21d8-aa79-e530-20f9d1c73fc8 ms:mtpsurl: https://msdn.microsoft.com/library/JJ248870(v=office.15) ms:contentKeyID: 48543287 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="68541-102">master ms:assetid: 101b2ce1-21d8-aa79-e530-20f9d1c73fc8 ms:mtpsurl: https://msdn.microsoft.com/library/JJ248870(v=office.15) ms:contentKeyID: 48543287 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="68541-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="68541-103"><<<<<<< HEAD</span></span>
# <a name="bookmark-property-ado"></a><span data-ttu-id="68541-104">Bookmark 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="68541-104">Bookmark Property (ADO)</span></span>
=======
# <a name="bookmark-property-ado"></a><span data-ttu-id="68541-105">Bookmark 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="68541-105">Bookmark property (ADO)</span></span>
>>>>>>> <span data-ttu-id="68541-106">master</span><span class="sxs-lookup"><span data-stu-id="68541-106">master</span></span>


<span data-ttu-id="68541-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="68541-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="68541-108">指示在 [Recordset](recordset-object-ado.md) 对象中唯一标识当前记录的书签，或者将 **Recordset** 对象中的当前记录设置为有效书签标识的记录。</span><span class="sxs-lookup"><span data-stu-id="68541-108">Indicates a bookmark that uniquely identifies the current record in a [Recordset](recordset-object-ado.md) object or sets the current record in a **Recordset** object to the record identified by a valid bookmark.</span></span>

<span data-ttu-id="68541-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="68541-109"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="68541-110">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="68541-110">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="68541-111">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="68541-111">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="68541-112">master</span><span class="sxs-lookup"><span data-stu-id="68541-112">master</span></span>

<span data-ttu-id="68541-113">设置或返回一个 **Variant** 表达式，该表达式的计算结果为一个有效书签。</span><span class="sxs-lookup"><span data-stu-id="68541-113">Sets or returns a **Variant** expression that evaluates to a valid bookmark.</span></span>

## <a name="remarks"></a><span data-ttu-id="68541-114">备注</span><span class="sxs-lookup"><span data-stu-id="68541-114">Remarks</span></span>

<span data-ttu-id="68541-p101">使用 **Bookmark** 属性可以保存当前记录的位置并随时返回到该记录处。书签仅在支持书签功能的 **Recordset** 对象中可用。</span><span class="sxs-lookup"><span data-stu-id="68541-p101">Use the **Bookmark** property to save the position of the current record and return to that record at any time. Bookmarks are available only in **Recordset** objects that support bookmark functionality.</span></span>

<span data-ttu-id="68541-p102">当打开 **Recordset** 对象时，它的每条记录都有一个唯一的书签。若要保存当前记录的书签，请将 **Bookmark** 属性的值赋给一个变量即可。若要在移动到不同的记录后随时快速返回到该记录，请将 **Recordset** 对象的 **Bookmark** 属性设置为该变量的值。</span><span class="sxs-lookup"><span data-stu-id="68541-p102">When you open a **Recordset** object, each of its records has a unique bookmark. To save the bookmark for the current record, assign the value of the **Bookmark** property to a variable. To quickly return to that record at any time after moving to a different record, set the **Recordset** object's **Bookmark** property to the value of that variable.</span></span>

<span data-ttu-id="68541-p103">用户可能无法查看书签的值。另外，用户不应期望可直接对书签进行比较  引用相同记录的两个书签可能具有不同的值。</span><span class="sxs-lookup"><span data-stu-id="68541-p103">The user may not be able to view the value of the bookmark. Also, users should not expect bookmarks to be directly comparable — two bookmarks that refer to the same record may have different values.</span></span>

<span data-ttu-id="68541-p104">如果使用 [Clone](clone-method-ado.md) 方法创建 **Recordset** 对象的副本，原始和重复 **Recordset** 对象的 **Bookmark** 属性设置是完全相同的，可以将二者交换使用。不过，无法将不同 **Recordset** 对象的书签交换使用，即使它们使用相同的源或命令创建也不行。</span><span class="sxs-lookup"><span data-stu-id="68541-p104">If you use the [Clone](clone-method-ado.md) method to create a copy of a **Recordset** object, the **Bookmark** property settings for the original and the duplicate **Recordset** objects are identical and you can use them interchangeably. However, you cannot use bookmarks from different **Recordset** objects interchangeably, even if they were created from the same source or command.</span></span>

<span data-ttu-id="68541-124">**远程数据服务用法**当客户端**Recordset**对象上使用， **Bookmark**属性始终是可用。</span><span class="sxs-lookup"><span data-stu-id="68541-124">**Remote Data Service Usage**When used on a client-side **Recordset** object, the **Bookmark** property is always available.</span></span>

