<?php
///////////////////////////////////////////////////////////////////////
// This class is used to generate a list of prime numbers from       //
// a supplied number range. You can then randomly select a number of //
// prime numbers from this list.                                     //
// Tom Scott                                                         //  
///////////////////////////////////////////////////////////////////////

class primeGenerator{
    
    private $start;
    private $end;
    private $modulus;
    private $primeArray = array();
    private $selectedPrimeArray = array();
    private $counter = 0;
    private $error = "Not enough prime numbers within the range selected";
    
    function __construct($start=null, $end=null){
        $this->start = (isset($start)) ? $start : 1;
        $this->end = (isset($end)) ? $end : 100;
        $this->generatePrime();
    }
    
    private function generatePrime(){
        for($i=$this->start;$i<=$this->end;$i++){
          $this->modulus = 0; 
            for($j=1;$j<=$i;$j++){
                if($i % $j==0){ 
                    $this->modulus++;
                }
            }
            if($this->modulus==2){
			     $this->primeArray[] = $i;
                 $this->counter++;
	        }
        }
    }
    
    public function getPrimeNumberRange(){
        return $this->primeArray;
    }
    
    public function getRandomPrimes($int=1){
        if($int <= 1){
            $this->selectedPrimeArray[] = $this->primeArray[array_rand($this->primeArray)];
        }else{
            if($int>$this->counter){
                throw new Exception($this->error);
            }else{
                $selected = array_rand($this->primeArray, $int);
                foreach($selected as $extract){
                    $this->selectedPrimeArray[] = $this->primeArray[$extract];
                }
            }
        }
            
        return $this->selectedPrimeArray;
    }
}
//Initiate class with a range, default 1 - 100
$prime = new primeGenerator(300,500);
//Function returns an array of all prime numbers within selected range
$range = $prime->getPrimeNumberRange();
//Function returns an array of random prime numbers within the initiated range
//Number of prime numbers required is passed as an argument. NOTE - the amount required; 
//there must be enough available within the range selected
$randNumbers = $prime->getRandomPrimes(16);
?>
