# trackingapp1
tracking app

Product.java
public class Product implements
Comparab|e<Product> {

private String name; private String type;

private int quantity; private double cost; @Override
public String toString() {

return "Product [name=" + name + ", type=" + type +
", quantity:" + quantity + ", cost=" + cost + "1";

} /** * @param name * @param type

* @param quantity * @param cost */

public Product(String name, String type, int quantity,
double cost) {

this.name = name; this.type = type;

this.quantity = quantity; this.cost = cost; }

public String getName() {return name; }

public void setName(String name) {

this.name = name; } public String getType(){

return type; } public void setType(String type) {
this.type 2 type; } public int getQuantityO {

return quantity; }

public void setQuantity(int quantity) {

this.quantity = quantity; } public double getCost() {
return cost; } public void setCost(double cost) {
this.cost 2 cost; } @Override public int hashCode() {
final int prime = 31; int result = 1; long temp;

temp = Double.doubleToLongBits(cost);

result: prime * result + (int) (temp "(temp >>> 32));
result: prime * result + ((name 2: null)? O:
name.hashCode());

result = prime * result + quantity;

result: prime * result + ((type =2 null) ? 0:
type.hashCode());

public boolean equals(Object obj) {if (this == obj)
return true; if (obj == null) return false;

if (getClass() != obj.getClass()) return false;
Product other 2 (Product) obj;
System.out.println(name+" "+other.name);
System.out.println(type+" "+other.type);
System.out.println(quantity+" "+other.quantity);
System.out.println(cost+" "+other.cost);

if (Double.doubleToLongBits(cost) !=
Double.doubleToLongBits(other.cost))

return false; if (name =2 null) {if (other.name != null)
return false; } else if (!name.equals(other.name))


return false; if (quantity != other.quantity)

return false; if (type == null) {if (other.type != null)
return false; } else if (ltype.equals(other.type))
return false; return true; } @Override

public int compareTo(Product p) {

return cost<p.getCost()?1:-”1;} public void display() {
System.out.println("Product Name:"+ name);
System.out.println("Product Type:"+ type);
System.out.println("Product Quantity:"+ quantity);
System.out.println("Product Cost:"+ cost); }}
TestApgjï¬‚ import java.util.lterator;

import java.util.Scanner; import java.util.Set;

import java.util.TreeSet; public class TestApp{
public static void main(String[] args) {
Set<Product> prodSet=new TreeSet<Product>();
String name; String type; int quantity; double cost;
Product p; Scanner sc=new Scanner(System.in);
System.out.println("Enter how many products do you
want in inventoryâ€ );

int prodCount:sc.nextlnt(); int availableProantzo;
int choice; boolean isProdFound=fa|se; while(true){
System.out.println("Please choose your option");
System.out.println("1. Add Product");
System.out.println("2. Get All Products");
System.out.println("3. Remove Products from
Inventory By Name");

System.out.println("4. Find No. of Laptops, Servers
and Desktops");

System.out.println("5. Computer with maximum
costâ€ );

System.out.println("6. Quit"); choice:sc.nextlnt();
switch (choice) {case 1:
if(avai|ableProant!=prodCount){
System.out.println("Please enter product name");
name=sc.next();

System.out.println("Please enter product type");
type=sc.next();

System.out.println("Please enter product quantity" );
quantity:sc.nextlnt();

System.out.println("Please enter product cost");
cost=sc.nextDouble();

p=new Product(name, type, quantity, cost);
prodSet.add(p); availableProant++;
System.out.println("Product is added to the inventory
successfully!!!");

}else{ System.out.println("|nventory is full!!!");}
break; case 2:
for (Iterator<Product> iterator : prodSet.iterator();
iterator.hasNext();) {
Product product = (Product) iterator.next();
product.disp|ay();
System.out.println("********************"); } break;
case 3:
System.out.println("Please enter product name");
name=sc.next();
for (Iterator<Product> iterator = prodSet.iterator();
iterator.hasNext();) {
Product product = (Product) iterator.next();
if(product.getName().equals(name)){
isProdFound=true; prodSet.remove(product);
System.out.println("Item is removed from inventory
successfully!!!");
availableProant--; break; }}if(!isProdFound)
System.out.println("could not find the product in the
inventory with the given name");
break; case 4: int laptoant=O; int desktoantzo;
int serverCnt=O;
for (Iterator<Product> iterator = prodSet.iterator();
iterator.hasNext();) {
Product product 2 (Product) iterator.next();
if(product.getType().equalslgnoreCase("laptop")){
laptoant++;
}else
if(product.getType().equalslgnoreCase("desktop")){
desktoant++;
}else
if(product.getType().equalslgnoreCase("server")){
serverCnt++;} }
System.out.println("Available laptops::"+laptoant);
System.out.println("Available
desktops::"+desktoant);
System.out.println("Available servers::"+serverCnt);
break; case 5:
for (Iterator<Product> iterator = prodSet.iterator();
iterator.hasNext();) {
Product product = (Product) iterator.next();
if(product.getName().equalslgnoreCase("computer"))
{
System.out.println("Computer with maximum cost
is::");

product.display(); break; } } break; case 6:
System.exit(0); break; default: break; }} }}
