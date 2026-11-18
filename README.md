QUESTION 1
for (int row = 0;row <sales.length;row++)
        {
            int productTotal = 0;
            
            for (int col = 0;col <sales[row].length;row++)
            {
                productTotal = 0;
                
                for (int col = 0;col <sales[row].length; col++)
                {
                    productTotal += sales[row][col];
                }
                
                if (productTotal > highestSales)
                {
                    highestSales = productTotal;
                    popularIndex = row;
                }
            }
            
            return productNames[popularIndex]+ "(" + highestSales +")";
        }
    }
}

import java.util.Scanner;

public class ProductSalesReport
{
    public static void main(String[]args)
    {
        Scanner input = new Scanner(System.in);
        
        //Single-dimension array
        String[] productNames =
        {
            "Cozy Nights Monarch mattress",
            "Restonic Barbados mattress",
            "Sealy Phuket mattress",
        };
        
        //Two-dimensional array: 3 products x 3 months
        int[][] sales = new int [3][3];
        
        //input sales data
        for (int row = 0; row <productNames.length; row++)
        {
            for (int col = 0;col <3; col++)
            {
                System.out.print("Enter number of sales for month "+ (col + 1)+ "for"+ productNames[row]+ ":");
                sales[row][col] = input.nextInt();
            }
            
            System.out.print();
        }
        
        //Create Product objectt
        Product product = new Product(productNames,sales);
        
        //Display report
        System.out.println("PRODUCT SALES REPORT-2026");
        
        System.out.println("**********************************");
        
        System.out.println("TOTAL PRODUCT SALES: "+ product.GetTotalSales());
        
        System.out.println("AVERAGE PRODUCT SALES: "+ Math.round(product.GetAverageSales()));
        
        System.out.println("MOST POPULAR PRODECT: "+product.GetMostPopularProduct());
        
        input.close();
    }
}

public class PrintProduct
{
    private Product product;
    
    //Constructor 
    public PrintProduct(Product product)
    {
        this.product  = product;
    }
    
    //Print total product sales
    public void PrintTotalProductales()
    {
        System.out.println("TOTAL PRODUCT SALES: "+ product.GetTotalProductsSold());
    }
    
    //Print average product sales
    public void PrintAverageProductSales()
    {
        System.out.println("AVERAGE PRODUCT SALES: "+ product.GetAverageProductSold());
    }
    
    //Print most popular product
    public void PrintMostPopularProduct()
    {
        System.out.println("MOST POPULAR PRODUCT SALES: "+ product.GetMostPopularProduct());
    }
    
    //Print the whole report
    public void PrintReport()
    {
        System.out.println("PRODUCT SALES REPORT-2026");
        
        System.out.println("*************************");
        
        PrintTotalProductSales();
        PrintAverageProductSales();
        PrintMostPopularProductSales();
    }
}

package tests;

import org.jpunit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

public class ProductTest
{
    @Test
    public void
            GetTotalProductSales_WithValidData_ReturnsCorrectValue()
            {
                String[] productNames =
                {
                    
            "Cozy Nights Monarch mattress",
            "Restonic Barbados mattress",
            "Sealy Phuket mattress",
                };
                
                int[][] sales =
                {
                    {25,18,20},
                    {15,10,12},
                    {1815,20},
                };
                
                Product product = new Product(productNames, sales);
                
                int expected = 153;
                        int actual = product.GetTotalProductsSold();
                        
                        assertEquals(expected, actual);
            }
            
            @Test
            public void
                    GetAverageSales_WithValidData_ReturnsCorrectValue()
                    {
                        String[] productNames =
                        {
                          "Cozy Nights Monarch mattress",
                            "Restonic Barbados mattress",
                            "Sealy Phuket mattress",
                        };
                        
                        int[][]sales =
                        {
                            {25,18,20},
                            {15,10,12},
                            {18,15,20},
                        };
                        
                        Product product = new Product(productNames, sales);
                        
                        double expected = 17.0;
                        double actual = product.GetAverageProductSold();
                        
                        assertEquals(expected, actual, 0.001);
                        }
                    }

                    QUESTION 2
                    public class mattresssalesapp extends javax.swing.JFrame {
    
    private static final java.util.logging.Logger logger = java.util.logging.Logger.getLogger(mattresssalesapp.class.getName());

    /**
     * Creates new form mattresssalesapp
     */
    public mattresssalesapp() {
        initComponents();
    }

    /**
     * This method is called from within the constructor to initialize the form.
     * WARNING: Do NOT modify this code. The content of this method is always
     * regenerated by the Form Editor.
     */
    @SuppressWarnings("unchecked")
    // <editor-fold defaultstate="collapsed" desc="Generated Code">                          
    private void initComponents() {

        jLabel1 = new javax.swing.JLabel();
        txtCustomer = new javax.swing.JTextField();
        jLabel2 = new javax.swing.JLabel();
        lblProduct = new javax.swing.JLabel();
        lblPrice = new javax.swing.JLabel();
        txtPrice = new javax.swing.JTextField();
        btnProcess = new javax.swing.JButton();
        jComboBox1 = new javax.swing.JComboBox<>();

        setDefaultCloseOperation(javax.swing.WindowConstants.EXIT_ON_CLOSE);

        jLabel1.setText("Customer Name :");

        txtCustomer.addActionListener(this::txtCustomerActionPerformed);

        lblProduct.setText("Select Product :");

        lblPrice.setText("Enter Price :");

        btnProcess.setText("Process");

        jComboBox1.setModel(new javax.swing.DefaultComboBoxModel<>(new String[] { "Cozy Nights Monarch", "Restonic Barbados", "Sealy Phuket" }));
        jComboBox1.addActionListener(this::jComboBox1ActionPerformed);

        javax.swing.GroupLayout layout = new javax.swing.GroupLayout(getContentPane());
        getContentPane().setLayout(layout);
        layout.setHorizontalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addGap(16, 16, 16)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.TRAILING)
                    .addGroup(layout.createSequentialGroup()
                        .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                            .addGroup(layout.createSequentialGroup()
                                .addGap(88, 88, 88)
                                .addComponent(jLabel2))
                            .addGroup(layout.createSequentialGroup()
                                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                                    .addComponent(lblPrice)
                                    .addComponent(lblProduct))
                                .addGap(91, 91, 91)
                                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.TRAILING, false)
                                    .addComponent(jComboBox1, javax.swing.GroupLayout.Alignment.LEADING, 0, 167, Short.MAX_VALUE)
                                    .addComponent(txtPrice, javax.swing.GroupLayout.Alignment.LEADING))))
                        .addContainerGap(javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE))
                    .addGroup(layout.createSequentialGroup()
                        .addComponent(jLabel1)
                        .addGap(80, 80, 80)
                        .addComponent(txtCustomer, javax.swing.GroupLayout.PREFERRED_SIZE, 184, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addGap(173, 173, 173))))
            .addGroup(javax.swing.GroupLayout.Alignment.TRAILING, layout.createSequentialGroup()
                .addContainerGap(javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
                .addComponent(btnProcess, javax.swing.GroupLayout.PREFERRED_SIZE, 159, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addGap(181, 181, 181))
        );
        layout.setVerticalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addGap(107, 107, 107)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(jLabel1)
                    .addComponent(txtCustomer, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.UNRELATED)
                .addComponent(jLabel2)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED, 27, Short.MAX_VALUE)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addComponent(lblProduct, javax.swing.GroupLayout.Alignment.TRAILING)
                    .addComponent(jComboBox1, javax.swing.GroupLayout.Alignment.TRAILING, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addGap(18, 18, 18)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(txtPrice, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(lblPrice))
                .addGap(56, 56, 56)
                .addComponent(btnProcess)
                .addGap(66, 66, 66))
        );

        pack();
    }// </editor-fold>                        

    private void txtCustomerActionPerformed(java.awt.event.ActionEvent evt) {                                            
        // TODO add your handling code here:
    }                                           

    private void jComboBox1ActionPerformed(java.awt.event.ActionEvent evt) {                                           
        // TODO add your handling code here:
    }                                          

    /**
     * @param args the command line arguments
     */
    public static void main(String args[]) {
        /* Set the Nimbus look and feel */
        //<editor-fold defaultstate="collapsed" desc=" Look and feel setting code (optional) ">
        /* If Nimbus (introduced in Java SE 6) is not available, stay with the default look and feel.
         * For details see http://download.oracle.com/javase/tutorial/uiswing/lookandfeel/plaf.html 
         */
        try {
            for (javax.swing.UIManager.LookAndFeelInfo info : javax.swing.UIManager.getInstalledLookAndFeels()) {
                if ("Nimbus".equals(info.getName())) {
                    javax.swing.UIManager.setLookAndFeel(info.getClassName());
                    break;
                }
            }
        } catch (ReflectiveOperationException | javax.swing.UnsupportedLookAndFeelException ex) {
            logger.log(java.util.logging.Level.SEVERE, null, ex);
        }
        //</editor-fold>

        /* Create and display the form */
        java.awt.EventQueue.invokeLater(() -> new mattresssalesapp().setVisible(true));
    }

    // Variables declaration - do not modify                     
    private javax.swing.JButton btnProcess;
    private javax.swing.JComboBox<String> jComboBox1;
    private javax.swing.JLabel jLabel1;
    private javax.swing.JLabel jLabel2;
    private javax.swing.JLabel lblPrice;
    private javax.swing.JLabel lblProduct;
    private javax.swing.JTextField txtCustomer;
    private javax.swing.JTextField txtPrice;
    // End of variables declaration                   
}
