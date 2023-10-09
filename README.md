public class CameraTechnologyReport {
    public static void main(String[] args) {
        String[] manufacturers = {"CANON", "SONY", "NIKON"};
        int[][] cameraPrices = {
            {10500, 8500},  // Canon
            {9500, 7200},   // Sony
            {12000, 8000}   // Nikon
        };

        System.out.println("Camera Technology Report");
        System.out.println("Manufacturer\t\tMirrorless\tDSLR\tDifference");

        int maxDifference = 0;
        String manufacturerWithMaxDifference = "";

        for (int i = 0; i < manufacturers.length; i++) {
            String manufacturer = manufacturers[i];
            int mirrorlessPrice = cameraPrices[i][0];
            int dslrPrice = cameraPrices[i][1];
            int difference = mirrorlessPrice - dslrPrice;

            System.out.printf("%-15s\tR %d\tR %d\tR %d", manufacturer, mirrorlessPrice, dslrPrice, difference);
            if (difference >= 2500) {
                System.out.print(" ***");
            }
            System.out.println();
            
            if (Math.abs(difference) > Math.abs(maxDifference)) {
                maxDifference = difference;
                manufacturerWithMaxDifference = manufacturer;
            }
        }

        System.out.println();
        System.out.println("Manufacturer with the greatest cost difference: " + manufacturerWithMaxDifference);
    }
}
